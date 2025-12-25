# Shraddha Monthly Donation Pledge Management (Dummy Project)

## Purpose
This dummy project is a small but representative slice of a larger donation-management system. It is used to evaluate external development teams for quality, delivery, documentation, and testing standards.

## Tech Stack
- Backend: Laravel (latest LTS)
- Frontend: Vue 3
- Database: MySQL 
- API: REST (documented)

## Domain Summary
This application manages monthly pledge-based donations for Shraddha Media Network. A pledge is **not** a subscription; donors can donate for any month(s) they choose and may skip months without penalty.

## Core Actors and Roles
- **Operator**: Adds donors and donation records, edits records with remarks, and can request soft-deletes.
- **Admin**: Manages operators, views all reports, and approves or permanently deletes records.
- **Viewer**: Read-only access to donor profiles and reports.
- **Donor (Portal User)**: Can view their own donation history only.

## Key Functional Requirements
### Donor Management
- Register a new donor.
- Search donors by NIC, Donor ID, name (English/Sinhala), phone, email, or address.
- Create a donor inline while adding a donation record (no forced page hopping).

### Donation Recording
- Donation methods:
  1. **Cash (Office)**: Must issue a printable bill at the time of entry.
  2. **Bank Transfer**: Capture bank, amount, transfer date, informed date, and informed type (WhatsApp, email, post). No bill; store an SMS message record (send not required).
- Allow donations to be recorded for multiple months at once (e.g., Jan + Feb). Donors may skip months.
- Display last paid month and paid-month history per donor.

### Billing and Receipts
- Cash payments require an immediate, printable bill.
- Printed output must be clean and production-ready.

### Editing, Deletion, and Audit
- **Soft delete** for operator deletions; admin approval required for permanent deletion.
- Operator edits must include a remark.
- Maintain edit history: editor name, original values, updated values, timestamp, and remark.
- Admin receives a notification when an operator deletes a record.

### Reports
- Daily, monthly, yearly, and custom date-range reports.
- Report breakdowns:
  - Cash vs bank totals
  - Operator added record count
  - Bank transfer details by bank and informed type

### Donor Portal
- Donors can log in to view only their own donation history.

## API Documentation Requirements
- Provide detailed API documentation (endpoints, parameters, validation rules, response examples).
- Include setup and deployment steps.

## Testing Requirements
- Laravel unit tests
- Feature tests
- Browser tests (e.g., Dusk or equivalent)
- Test coverage must include: donor creation, cash payment + bill, bank transfer + SMS record, edit with remark, soft delete flow, and reports.

## Non-Functional Requirements
- User-friendly, linear data-entry flow (minimize page changes while adding a donation).
- Clean and maintainable codebase.
- Clear change log for each feature delivery.
- Documentation must allow another team to continue development without dependency on the original developers.

## Deliverables
- Source code (Laravel + Vue)
- API documentation
- Code documentation
- Change log
- User guide
- Automated test suite

## Acceptance Criteria
- All core features implemented per spec.
- Tests passing.
- Documentation complete and clear.
- Application deployable on a clean environment using provided instructions.

## Notes
This is a **dummy project** for evaluation. The delivered code must be production-quality, testable, and maintainable.
