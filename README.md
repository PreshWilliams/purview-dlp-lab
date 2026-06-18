# Microsoft Purview DLP & Data Governance Lab

A hands-on lab that classifies data, detects sensitive information, and catches it leaving the organisation, built on Microsoft Purview for a fictional UK business (Northwind Cinemas Ltd) using synthetic data in an isolated test area.

Report by Presh Williams

## The problem

Sensitive data does not only leak outward. As organisations adopt AI, it also gets over-exposed inward, surfaced to a person or system that has access but no business need. A tool like Microsoft 365 Copilot can read whatever a user can open, so an over-shared payroll file or a customer list a leaver still has access to can end up summarised in an answer.

## The thesis

Classify the data once, then act on that classification everywhere it moves, including AI. Sensitivity labels carry the classification; DLP and label-based controls enforce the handling rules at every point of egress.

## What I built (configured and evidenced)

- A four-tier classification scheme: Public, Internal, Confidential, Highly Confidential.
- Sensitivity labels with mandatory labelling (default Public, justification required to downgrade).
- Auto-labelling that classifies PII and payment data by content (UK National Insurance Number to Confidential, Credit Card Number to Highly Confidential).
- A DLP policy in audit mode across Exchange, SharePoint, and OneDrive.
- A worked incident-triage walkthrough using a real detection.

## What I designed (documented, not configured)

- Endpoint DLP (USB, unmanaged upload, print).
- AI/Copilot data-leakage controls (DLP for the Microsoft 365 Copilot location, DSPM for AI).
- Label-based encryption.

Each carries its licensing or device-onboarding dependency, stated honestly rather than implied as built.

## Frameworks mapped

UK GDPR / DPA 2018 (as amended by the DUAA 2025), Cyber Essentials, ISO/IEC 27001:2022, ISO/IEC 42001, EU GDPR, and the EU AI Act as an anchor.

## The result that matters

Content inspection caught a Highly Confidential customer list leaving in an outbound email that the user had labelled only Public. The label was wrong; the detection was not. That is the thesis in practice.

## Repository contents

- `Implementation_Runbook_Northwind_Cinemas.md` — the full runbook (renders on GitHub with the `images/` folder).
- `Implementation_Runbook_Northwind_Cinemas.html` — the same runbook as a single self-contained file with all screenshots embedded.
- `images/` — redacted screenshots used as evidence.

## A note on data and privacy

Every document, identifier, and value in this lab is fictional or non-issued. Screenshots are redacted to remove tenant, domain, and account details before publication.
