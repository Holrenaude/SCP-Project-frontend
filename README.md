# Supplier Consumer Platform (SCP) - Frontend

## Overview
The Supplier Consumer Platform (SCP) is a B2B platform enabling direct collaboration between food suppliers and institutional consumers (restaurants, hotels). This frontend implements:

- **Web interface for suppliers** (Owners, Managers, Sales Representatives)
- **Mobile app for consumers and Sales Representatives**

The MVP focuses on core Supplier ↔ Consumer workflows: catalog management, ordering, complaint handling, and communication.

## Features

### Consumer (Mobile)
- Request link to supplier account
- View catalog after approval
- Place and track orders
- Log complaints tied to orders
- Chat with attachments and canned messages

### Supplier (Web)
#### Roles & Permissions
- **Owner:** Full control, manage managers, delete account
- **Manager:** Catalog & inventory management, complaint escalation
- **Sales Rep:** Handles consumer communication, first-line complaints

#### Catalog & Order Management
- Create/edit products (price, units, stock, delivery options)
- Accept/reject orders, update stock in real time
- Handle complaints: Sales → Manager → Owner

#### Communication
- Integrated chat
- Link management: approve/block/unlink consumers

### Optional (Platform Admin)
- Supplier verification and moderation
- Analytics dashboards

## Technology Stack
- **Web:** React (Next.js) + Tailwind CSS
- **Mobile:** Flutter or React Native
- **Backend:** REST API (Django/FastAPI/Spring/Go), PostgreSQL
- **Design:** Figma
- **Deployment:** Docker containers

## Use Cases
1. Consumer places an order → appears in supplier dashboard
2. Sales Rep handles a complaint → escalates to Manager if unresolved
3. Manager updates catalog → visible to linked consumers
4. Owner creates Manager account → account active immediately
5. Owner deletes supplier account → account deactivated and archived

## Role Responsibility Matrix (RACI)
| Task                           | Owner | Manager | Sales | Consumer | Platform Admin |
|--------------------------------|-------|---------|-------|---------|----------------|
| Supplier account creation/deletion | A     |         |       | I       | I              |
| Manage Manager accounts          | A     |         |       | I       | I              |
| Catalog & inventory management   | R/A   | R/A     |       | I       | C              |
| Consumer inquiries               | I     | C       | R/A   | C       | I              |
| Place order                      | I     | I       | I     | R/A     | I              |
| Accept/reject order              | C     | R/A     | C     | I       | I              |
| First-line complaint handling    | I     | C       | R/A   | C       | I              |
| Complaint escalation             | C     | R/A     | C     | C       | I              |
| Supplier verification (optional) | I     | I       | I     | I       | R/A            |
| Catalog moderation (optional)    | I     | I       | I     | I       | R/A            |
| Analytics dashboards (optional)  | I     | I       | I     | I       | R/A            |

R = Responsible, A = Accountable, C = Consulted, I = Informed

## Deployment
- Development: `npm start` / `yarn dev` (React) or Flutter/React Native for mobile
- Production: Docker containers recommended, cloud hosting optional

