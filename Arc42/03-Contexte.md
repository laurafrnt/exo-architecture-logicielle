# 3. System Context

## 3.1 Business Context
Describe how the system interacts with business processes, users, or organizations.

**Example:**
The platform provides online booking for workshops.  
It interacts with:
- Customers (via web app)
- Payment provider (Stripe)
- CRM system (Salesforce)

### Actors and Interfaces
| Actor | Interaction | Purpose |
|--------|--------------|----------|
| Customer | Web app | Book and pay for services |
| Admin | Back office | Manage sessions and users |
| Payment Service | API | Process transactions |

## 3.2 Technical Context
Explain the technical boundaries and integrations. Include a diagram if possible.

```mermaid
graph TD
  User -->|HTTPS| WebApp
  WebApp -->|REST API| Backend
  Backend -->|SQL| PostgreSQL
  Backend -->|API| Stripe
