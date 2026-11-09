# Card Fraud & Chargeback Analysis

Business analysis for **card-not-present fraud detection**, **issuer dispute handling**, and **chargeback representment** workflows.

## Purpose

Documents how a BA defines requirements for fraud scoring integration, customer dispute journeys, and scheme-compliant chargeback processing (Visa/Mastercard reason codes).

## Contents

| Document | Description |
|----------|-------------|
| [Domain Overview](docs/01-domain-overview.md) | Fraud vs disputes vs chargebacks |
| [As-Is Process Analysis](docs/02-as-is-process-analysis.md) | Dispute and chargeback lifecycle |
| [Business Requirements Document](docs/03-business-requirements-document.md) | BRD for dispute management platform |
| [User Stories & Acceptance Criteria](docs/04-user-stories-and-acceptance-criteria.md) | Customer and ops user stories |
| [Stakeholder Analysis](docs/05-stakeholder-analysis.md) | Fraud ops, customer service, schemes |
| [Glossary](docs/06-glossary.md) | Fraud and chargeback terms |
| [To-Be Process Design](docs/07-to-be-process-design.md) | Review findings, credit decision table, scheme reference, evidence |
| [Worked Scenarios](docs/08-worked-scenarios.md) | Fraud, 3DS, duplicates, representment, financial impact |
| [Data and Test Plan](docs/09-data-and-test-plan.md) | Case record, status model, alert triage, metrics, UAT |
| [Requirements Traceability Matrix](artifacts/requirements-traceability-matrix.md) | Traceability matrix |

## Skills Demonstrated

- Scheme rules translation (timelines, reason codes, compelling evidence)
- Customer journey mapping for disputes
- Fraud alert triage and false-positive reduction requirements
- Financial impact analysis (chargeback ratios, representment win rates)
- Ops efficiency metrics (SLA, auto-write-off thresholds)
- Requirements quality review, with findings closed through change requests
- Worked numeric scenarios, edge case registers, and boundary-level UAT plans

## Disclaimer

Fictional scenarios for portfolio demonstration.
