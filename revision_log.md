# Revision Log for “Review & Refine with AI”

Este documento recoge todas las iteraciones de revisión de los artefactos `tech_spec.md` y `system_architecture.mmd`. Cada sección incluye el prompt enviado al AI, la respuesta recibida y los cambios aplicados.

---

## 1. Data Model Audit

**Prompt**  
> You are a senior architect. Review the data models section in `tech_spec.md`.  
> 1. What audit fields are missing?  
> 2. How would you optimize for high-volume queries (1M+ users)?  

**AI response**  
1. Faltan campos de auditoría: `createdAt`, `updatedAt`, `createdBy`, `updatedBy` en todas las entidades.  
2. Sugiere Global Secondary Indexes (GSIs) en DynamoDB:  
   - GSI por `Tasks.createdBy`  
   - GSI por `Notifications.scheduledFor`  
3. Recomienda particionar por hash de `userId` combinado con mes de `dueDate` para distribuir la carga.

**Applied Changes in `tech_spec.md`**  
```diff
 ### Users
 | Attribute    | Type    | Notes                                  |
 |--------------|---------|----------------------------------------|
 | userId       | string  | Primary key                            |
-| name         | string  |                                        |
+| name         | string  |                                        |
+| createdAt    | ISODate | Timestamp de creación                  |
+| updatedAt    | ISODate | Timestamp de última modificación       |
+| createdBy    | string  | FK → Users.userId                      |
+| updatedBy    | string  | FK → Users.userId                      |

 ### Tasks
 | Attribute     | Type     | Notes                              |
 |---------------|----------|------------------------------------|
 | taskId        | string   | Primary key                        |
+| createdAt     | ISODate  | Timestamp de creación              |
+| updatedAt     | ISODate  | Timestamp de última modificación   |
 | dueDate       | ISODate  |                                    |
 | createdBy     | string   | FK → Users.userId                  |
