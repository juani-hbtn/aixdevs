# Plan Summary for FamilyTask AI

---

## 1. Product Vision and Goals

**FamilyTask AI** is a cross-platform web and mobile application that helps families and shared households assign, track, and complete chores collaboratively. Leveraging AI-driven reminders and light gamification, it ensures:

- **Clarity:** Everyone sees their responsibilities in a single dashboard.  
- **Reliability:** Smart reminders adapt to each user’s schedule and habits.  
- **Engagement:** Points and badges motivate consistent participation.  
- **Flexibility:** Guest access via one-time links without full registration.

---

## 2. User Stories Overview and Prioritization

### MVP (High Priority)
1. **As a Parent Coordinator, I want to assign tasks**, so that responsibilities are clearly distributed.  
2. **As a Teenager, I want to view and complete my tasks**, so that I know what to do.  
3. **As a Roommate, I want to reassign chores**, so that household duties stay balanced.  
4. **As a Parent Coordinator, I want AI reminders 30 min before due**, so I don’t forget.  
5. **As a Roommate, I want a daily digest of tasks**, so I’m not overwhelmed by notifications.

### Nice-to-Have (Medium Priority)
- Teenagers earn points and see a leaderboard.  
- Parent awards streak badges.  
- Guests complete tasks via temporary link.

### Future (Low Priority)
- Google Calendar sync.  
- Voice reminders via Alexa/Google Assistant.

---

## 3. Key Technical Decisions and Architecture

- **Frontend:** React + TypeScript (hosted on S3 + CloudFront) for responsive UI.  
- **API Layer:** AWS Lambda (Node.js) + API Gateway for a fully serverless backend.  
- **Data Storage:** DynamoDB with Global Secondary Indexes and DAX cache for hot queries.  
- **Auth & Security:** AWS Cognito user pools + single-use guest tokens scoped to assignments.  
- **AI Engine:** Amazon SageMaker/OpenAI for dynamic scheduling logic.  
- **Notifications:** EventBridge scheduler + SNS/SQS batching for high-volume reminders.

---

## 4. Diagram Walkthrough and Component Explanations

```mermaid
flowchart LR
  subgraph Frontend
    A[React App]
  end
  subgraph API
    B[API Gateway] --> C[AWS Lambda Functions]
  end
  subgraph Datastore
    D[(DynamoDB)]
    subgraph Cache
      G[(DAX Accelerator)]
    end
  end
  subgraph AI
    E[SageMaker / OpenAI API]
  end
  subgraph Scheduler
    F[EventBridge]
  end

  A -->|HTTPS| B
  C --> D
  C --> G
  C -->|Invoke| E
  F --> C
