# Compliance-locked AR prototype

Volopay Founder's Office assignment. Live demo: https://anuvindakral.github.io/volopay-assignment-prototype/

A single-file browser prototype for UAE e-invoicing. An invoice is checked against the official Ministry of Finance mandatory-fields list before it leaves the AR workflow, then exchanged with a simulated Accredited Service Provider (ASP). If the provider rejects it, the diagnosis and the fix happen in the same screen as the invoice.

## Why this focus

Creating an invoice is only one part of getting paid. An invoice can be rejected because a required field is missing or the data does not match the expected format. When that happens, the finance team needs to understand the issue, fix it and submit the invoice again.

This prototype focuses on that part of the workflow: making errors easier to understand and giving the user a clear path to recovery.

## Try the live demo

Open https://anuvindakral.github.io/volopay-assignment-prototype/ in any browser. No install, no login, no local setup. Sample data is used throughout; no real invoices are sent.

Two flows are worth trying:

- **Fix a validation error.** Load "Rejected: buyer details", correct the flagged buyer TRN and e-invoice address, and submit again. The invoice stays blocked until both fields are fixed.
- **Recover from a rejection.** Load "Rejected: VAT mismatch", review the simulated provider rejection, press "Use the calculated total", and retry. The invoice then moves to accepted.

## What works

- Invoice creation and line-item editing
- Country-specific field checks for the UAE flow, cloned from the official MOF mandatory-fields list (v1.1, 28 Oct 2026)
- Required-field and invoice-total validation
- Field-level error messages and correction, with the invoice staying blocked until all issues are resolved
- Simulated provider acceptance and rejection, with two distinct gate layers (local check, then provider re-check)
- Invoice status and retry flow, including an accepted invoice that is never downgraded by a later failed attempt
- An invoice register with status and next step
- A responsive layout for smaller screens

## What is simulated

The provider responses are mocked to demonstrate how the workflow could behave. The prototype does not connect to a live e-invoicing provider, ERP, database or tax authority.

The validation rules demonstrate the intended interaction and should not be treated as a complete compliance engine, or as confirmation that an invoice is legally valid. All ASP and FTA interactions are simulated; sample companies are fictional.

## If this moved beyond a prototype

A production implementation would need a backend, persistent invoice records, authenticated access, secure handling of business data, provider integration, ERP synchronisation, monitoring, and proper testing against the relevant technical specifications.

The main question to test is whether clearer rejection messages and a guided correction flow reduce the time and effort finance teams spend resolving invoice issues.

## Files

- `index.html` - the entire prototype (HTML, CSS, JavaScript in one file)
- Live site: https://anuvindakral.github.io/volopay-assignment-prototype/
