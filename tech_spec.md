# Technical Specification for FamilyTask AI

## 1. System Overview
FamilyTask AI is built as a responsive web application (React) backed by a serverless API layer (Node.js + AWS Lambda) and a globally distributed NoSQL datastore (AWS DynamoDB). An AI-driven reminder engine schedules and adjusts task notifications.

## 2. High-Level Components
1. **Web Frontend**  
   - Framework: React + TypeScript  
   - Hosting: AWS S3 + CloudFront (static site)  
2. **API Layer**  
   - AWS Lambda (Node.js) behind API Gateway  
   - Endpoints for tasks, users, assignments, notifications  
3. **Datastore**  
   - AWS DynamoDB tables for Users, Tasks, Assignments, Notifications  
4. **AI Reminder Engine**  
   - AWS Lambda scheduled via EventBridge  
   - Uses Amazon SageMaker endpoint or OpenAI API for smart scheduling  
5. **Auth & Security**  
   - AWS Cognito for user pools and guest links  
   - Guest links as single-use UUID v4 tokens:  
     - Stored (hashed) in DynamoDB  
     - Expires 1 hour after issue or on first use  
     - JWT scope limited to `assignments:read-write`  
6. **Integrations**  
   - Calendar sync microservice (Lambda)  
   - Voice-assistant connector (Lambda + Alexa/Google Assistant SDK)  

## 3. Data Models

### Users
| Attribute    | Type    | Notes                                  |
|--------------|---------|----------------------------------------|
| userId       | string  | Primary key                            |
| name         | string  |                                        |
| email        | string  |                                        |
| role         | enum    | `PARENT`, `TEEN`, `ROOMMATE`, `CAREGIVER`, `GUEST` |
| createdAt    | ISODate | Timestamp de creación                  |
| updatedAt    | ISODate | Timestamp de última modificación       |
| createdBy    | string  | FK → Users.userId                      |
| updatedBy    | string  | FK → Users.userId                      |

### Tasks
| Attribute     | Type     | Notes                              |
|---------------|----------|------------------------------------|
| taskId        | string   | Primary key                        |
| title         | string   |                                    |
| description   | string   |                                    |
| dueDate       | ISODate  |                                    |
| createdBy     | string   | FK → Users.userId                  |
| createdAt     | ISODate  | Timestamp de creación              |
| updatedAt     | ISODate  | Timestamp de última modificación   |
| status        | enum     | `PENDING`, `COMPLETED`, `CANCELLED`|

### Assignments
| Attribute | Type   | Notes                           |
|-----------|--------|---------------------------------|
| assignId  | string | Primary key                     |
| taskId    | string | FK → Tasks.taskId               |
| userId    | string | FK → Users.userId               |
| timestamp | number | Assignment timestamp            |

### Notifications
| Attribute     | Type     | Notes                                   |
|---------------|----------|-----------------------------------------|
| notifyId      | string   | Primary key                             |
| assignId      | string   | FK → Assignments.assignId               |
| scheduledFor  | ISODate  | When the AI plans to send the reminder |
| status        | enum     | `SCHEDULED`, `SENT`, `SNOOZED`, `FAILED`|

## 4. API Endpoints

| Method | Path                                   | Description                                |
|--------|----------------------------------------|--------------------------------------------|
| POST   | `/users`                               | Create user or guest link                  |
| GET    | `/users/{userId}`                     | Retrieve user profile                      |
| POST   | `/tasks`                               | Create a new task                          |
| GET    | `/tasks/{taskId}`                     | Get task details                           |
| PATCH  | `/tasks/{taskId}`                     | Update task status or details              |
| GET    | `/users/{userId}/tasks`               | List tasks assigned to a user              |
| POST   | `/assignments`                         | Assign task to user                        |
| GET    | `/assignments/{assignId}`             | Get assignment info                        |
| GET    | `/notifications/{userId}`             | List upcoming notifications for a user     |
| POST   | `/notifications/{assignId}/snooze`    | Snooze a scheduled notification            |

## 5. Technology Justification

- **Serverless (Lambda + API Gateway)**: scales elastically, pay-per-execution  
- **DynamoDB**: single-digit millisecond reads/writes, auto-sharding  
- **Cognito**: built-in user pools + temporary guest links  
- **S3 + CloudFront**: global CDN for static front-end at low cost  
- **SageMaker/OpenAI**: flexible AI model hosting for reminder logic  

## 6. Constraints & Non-Functional Requirements

- **Mobile-first**: ensure UI/UX works on phones/tablets  
- **Availability**: 99.9% API uptime via AWS SLA  
- **Latency**: API calls < 150 ms p99; notification engine completes scheduling within 1 min  
- **Security**: end-to-end encryption (HTTPS + DynamoDB encryption at rest)  
- **Privacy**: user data segmented per family; guest data auto-deleted after 7 days  

## 7. AI Reminder Engine

- AWS Lambda scheduled via EventBridge  
- Mitigations for high-volume firing:  
  - Batch invocation (1 000 reminders per invocation)  
  - SNS + SQS buffer between scheduler and processors  
  - Exponential backoff and DLQ for failed reminders  
