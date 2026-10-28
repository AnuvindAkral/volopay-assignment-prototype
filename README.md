# Compliance-Locked AR — Concept Prototype (Volopay Founder's Office assignment)

Live: https://anuvindakral.github.io/volopay-assignment-prototype/

A single-file, zero-dependency browser prototype demonstrating a "compliance-locked invoicing" flow for UAE e-invoicing: invoices are pre-validated against the official Ministry of Finance *UAE Electronic Invoice Mandatory Fields* list (v1.1, 28 Oct 2026), then exchanged with a **simulated** Accredited Service Provider (ASP).

**All ASP / FTA interactions are simulated.** No real provider, network call, or tax authority is contacted. Sample companies are fictional.

## The journey
1. Create an invoice (seller, buyer, lines, VAT).
2. Trigger country-specific validation (rules cloned from the official MOF mandatory-fields list).
3. Encounter a rejection (try the sample buttons: invalid buyer TRN, or VAT breakdown mismatch).
4. Read the field-level diagnosis and fix guidance.
5. Correct and resubmit.
6. Observe the simulated ASP response: MLS status, TDD reporting, PINT-AE-shaped payload.
7. Check the register: accepted invoices hand off to the AR collections concept.

## Statuses
- IMPLEMENTED: form, validation engine, rejection handling, register, persistence (localStorage).
- SIMULATED: ASP exchange, MLS/TDD statuses.
- NOT BUILT: production submission rails, India leg, real AR collections/ERP sync (architecture described in the accompanying document).

Built for a hiring assignment; not production software.
