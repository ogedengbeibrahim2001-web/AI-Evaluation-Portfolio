# 04 — Automated Workflow & Routing Audit

## Overview
Audits an automated event-registration workflow (Form Trigger -> Text/Name Formatting -> Spreadsheet Row Logging -> Delay -> Branching Paths + Fallback) for routing accuracy, field-mapping integrity, string-matching edge cases, and privacy hygiene.

## Workflow Architecture Audited
- **Trigger:** New form submission intake
- **Formatting Steps:** Text normalization and name formatting
- **Logging & Delay:** Spreadsheet row creation followed by a timed delay before routing
- **Branching Logic:** Three event-specific branches plus a catch-all Fallback branch

## Key Audit Findings
- **Field-Mapping Defects:** Certain branch rules reference an email field instead of the event selection field, causing valid event registrations to miss intended branches.
- **Exact-Match Sensitivity:** `(Text) Exactly matches` rules are sensitive to casing and whitespace differences.
- **Fallback Coverage:** Unmatched inputs route to the Fallback branch, providing a safety net for unexpected values.
- **Privacy & Sanitization:** All repository fixtures and examples are anonymized with placeholder values and stripped of personal identifiers or account metadata.

## Artifacts
- `test-cases.csv` — 10 structured routing, formatting, and edge-case test definitions (`WF-01` to `WF-10`)
- `results.csv` — Audit outcomes, pass/fail status, defect severity, and remediation notes
