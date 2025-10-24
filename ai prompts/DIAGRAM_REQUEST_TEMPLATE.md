# 📊 Draw.io Diagram Request Template

Use this template when requesting Draw.io diagrams from AI assistants.

---

## **🎯 Quick Request Phrase (Copy & Use)**

```
Create a Draw.io diagram using the standard app.diagrams.net XML format for:
[YOUR TOPIC HERE]

Following this structure: [paste template below]
```

> **Important:** Always include the phrase **"using the standard app.diagrams.net XML format"** to ensure compatibility!

---

## **📝 Full Request Template**

```markdown
Create a Draw.io diagram using the standard app.diagrams.net XML format for:

**Topic/Workflow Name:** [e.g., User Authentication Flow, Database Schema, Payment Process]

**Main Components/Steps:**

1. [Component/Step 1]
2. [Component/Step 2]
3. [Component/Step 3]
4. [Add more as needed...]

**Decision Points/Branching:**

- [e.g., If user authenticated → success path, else → error path]
- [Add any conditional logic or branches]

**Annotations to Include:**

- [e.g., Status values, email notifications, API calls, database updates]
- [e.g., Timing information, user roles, data transformations]

**Color Coding Scheme:**

- 🟢 Green: [e.g., Success states, status boxes]
- 🔵 Blue: [e.g., Email notifications, external services]
- 🟣 Purple: [e.g., In-app notifications, user actions]
- 🟡 Yellow: [e.g., Backend actions, processing steps]
- 🔴 Red: [e.g., Error states, critical actions]
- ⚪ Gray: [e.g., Automated processes, system events]

**Flow Direction:** [Top-to-bottom / Left-to-right / Other]

**Additional Elements:**

- [ ] Include legend
- [ ] Add title/header
- [ ] Show data flow with arrows
- [ ] Include timestamps/dates
- [ ] Add summary section
- [ ] Other: ******\_\_\_******
```

---

## **💡 Example Requests**

### **Example 1: Workflow Diagram**

```markdown
Create a Draw.io diagram using the standard app.diagrams.net XML format for:

**Topic/Workflow Name:** E-commerce Checkout Process

**Main Components/Steps:**

1. Shopping cart review
2. Shipping information entry
3. Payment method selection
4. Order confirmation
5. Email receipt sent

**Decision Points/Branching:**

- If payment successful → Send confirmation email
- If payment fails → Show error and retry options
- If inventory unavailable → Notify user and suggest alternatives

**Annotations to Include:**

- Payment gateway API calls
- Email notifications sent at each stage
- Database updates (order status, inventory)
- User notifications (in-app and email)

**Color Coding Scheme:**

- 🟢 Green: Successful steps
- 🔵 Blue: Email/SMS notifications
- 🟡 Yellow: API calls
- 🔴 Red: Error/failure paths
- ⚪ Gray: Database updates

**Flow Direction:** Top-to-bottom

**Additional Elements:**

- [x] Include legend
- [x] Add title/header
- [x] Show data flow with arrows
- [ ] Include timestamps/dates
- [x] Add summary section
```

---

### **Example 2: System Architecture**

```markdown
Create a Draw.io diagram using the standard app.diagrams.net XML format for:

**Topic/Workflow Name:** Microservices Architecture

**Main Components/Steps:**

1. React Frontend (Web & Mobile)
2. API Gateway
3. Authentication Service
4. User Service
5. Order Service
6. Payment Service
7. PostgreSQL Database
8. Redis Cache
9. Message Queue (RabbitMQ)

**Decision Points/Branching:**

- Authentication check at gateway
- Cache hit/miss logic
- Async vs sync processing

**Annotations to Include:**

- REST API endpoints
- WebSocket connections
- Database queries
- Cache strategies
- Message queue topics

**Color Coding Scheme:**

- 🔵 Blue: Frontend layer
- 🟢 Green: Backend services
- 🟡 Yellow: Middleware (API Gateway)
- 🟣 Purple: Data stores
- 🔴 Red: External services

**Flow Direction:** Left-to-right

**Additional Elements:**

- [x] Include legend
- [x] Show data flow with labeled arrows
- [x] Group related services with containers/swimlanes
```

---

### **Example 3: Database Schema**

```markdown
Create a Draw.io diagram using the standard app.diagrams.net XML format for:

**Topic/Workflow Name:** Blog Platform Database Schema

**Main Components/Steps:**

1. users table
2. posts table
3. comments table
4. categories table
5. tags table
6. post_tags junction table

**Decision Points/Branching:**
N/A (this is a schema, not a process flow)

**Annotations to Include:**

- Primary keys (PK)
- Foreign keys (FK)
- Field types (VARCHAR, INT, TIMESTAMP)
- Relationships (one-to-many, many-to-many)
- Indexes

**Color Coding Scheme:**

- 🔵 Blue: Primary key fields
- 🟢 Green: Foreign key fields
- ⚪ Gray: Regular fields
- 🟡 Yellow: Indexed fields

**Flow Direction:** Top-to-bottom (hierarchical)

**Additional Elements:**

- [x] Include legend
- [x] Show relationships with labeled connectors
- [x] Use ERD notation (crow's foot)
```

---

## **✅ Checklist Before Requesting**

Before submitting your diagram request, ensure you have:

- [ ] Included the magic phrase: **"using the standard app.diagrams.net XML format"**
- [ ] Clearly defined the topic/workflow name
- [ ] Listed all main components or steps
- [ ] Specified decision points (if any)
- [ ] Defined what annotations to include
- [ ] Chosen a color coding scheme
- [ ] Specified flow direction
- [ ] Indicated which additional elements you want

---

## **🎨 Standard Color Palette**

Use these standard colors for consistency:

| Color           | Hex Code  | Use Case                      |
| --------------- | --------- | ----------------------------- |
| 🟢 Light Green  | `#d5e8d4` | Success, status boxes         |
| 🔵 Light Blue   | `#dae8fc` | Notifications, communication  |
| 🟣 Light Purple | `#e1d5e7` | In-app features, user actions |
| 🟡 Light Yellow | `#fff4e6` | Processing, backend actions   |
| 🔴 Light Red    | `#f8cecc` | Errors, critical actions      |
| ⚪ Light Gray   | `#e6e6e6` | Automated, system processes   |
| 🟠 Light Orange | `#ffe6cc` | Warnings, decisions           |

---

## **🚀 Quick Copy-Paste Starter**

```
Create a Draw.io diagram using the standard app.diagrams.net XML format for:

[YOUR WORKFLOW/SYSTEM NAME HERE]

Include [NUMBER] main steps/components with [describe key features like: decision points, notifications, status updates, etc.].

Use color coding: Green for [X], Blue for [Y], Yellow for [Z].

Flow direction: [top-to-bottom/left-to-right].

Include a legend.
```

---

## **📌 Tips for Best Results**

1. **Be specific** about what you want to visualize
2. **Define the color scheme** upfront - it makes diagrams clearer
3. **Mention decision points** explicitly if your workflow has branching
4. **Request a legend** - it makes diagrams self-documenting
5. **Specify annotations** - what extra info should appear on each box
6. **State the flow direction** - helps with layout planning
7. **Always use the magic phrase** about standard XML format!

---

## **🔧 Troubleshooting**

If your diagram doesn't load in Draw.io:

1. Check that you included: **"using the standard app.diagrams.net XML format"**
2. Ask: "Can you regenerate using the minimal Draw.io XML structure?"
3. Verify the file extension is `.drawio` (not `.xml` or `.txt`)

---

**Last Updated:** [Date]  
**Version:** 1.0  
**Compatible with:** app.diagrams.net / draw.io
