# Euro-Jobs Customer 360°

An English-language, interactive React + TypeScript prototype of a future Odoo 18 customer operations workspace. All records, amounts and trends are illustrative. No connection to Odoo, payroll, banking or real accounting is made.

## Run

```sh
npm install --cache /tmp/eurojobs-npm-cache
npm run dev
```

Build with `npm run build`. The development server listens on port 5173. No credentials are required.

## Explore

Dashboard, customer list and company record, factories, workforce assignments, requests, contracts, timesheets, billing, invoices, relations, reports, client preview and implementation blueprint.

Select September 2026 for the seeded journey. Open a customer, review a worksite, transfer a worker (previous assignment retained), create a request and record HQ approval. Review the disputed timesheet, select Customer approved and save. In Billing Preparation select a customer, check Finance approval and prepare one draft. Repeating creation is blocked. Posted sample invoices support simulated partial payments; draft invoices do not. Contacts have editable portal/confirmation permissions. CSV exports include sample invoices.

State is held in memory and resets on reload. Rates, dates, commercial rules and billing calculations are deliberately simplified for UI discussion. Assignment transfers update the current assignment view; historical reporting is not implemented. Rate dialogs and import/document previews are explicitly illustrative. No real attachments are uploaded or parsed. Client preview hides HQ navigation but is not production access control.

## Eventual Odoo implementation

Customer identity stays in `res.partner`, workers in `hr.employee`, attendance in existing time sources and invoices in `account.move`. Payments must come from accounting reconciliation. Audit existing factory, branch, recruitment and request custom models before introducing extensions. Production record rules, approvals, effective-dated pricing, multi-company accounting, VAT and integrations require separate engineering.

## Tickets, email, chatter and documents

The Tickets, Email & Chatter, and Documents screens are connected to each customer. Create tickets, assign owners, change status, add local messages and internal notes, and attach/download documents against a customer or ticket. These records persist in this browser's localStorage; they are not shared with other users. Documents are limited to 2 MB total, with clear storage failure feedback. Do not use sensitive production records in this demo.

Compose email saves a draft and opens the default email app using mailto. Actual sending happens in that app, not in the prototype; delivery and incoming replies are not tracked. Direct sending, shared ticketing, incoming email threading, private notes, secure document storage and access permissions require a real backend/Odoo connection. Customer portal preview does not expose the HQ communication workspace.
