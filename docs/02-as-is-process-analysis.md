# As-Is Process — Disputes & Chargebacks

```mermaid
sequenceDiagram
    participant Cust as Customer
    participant CS as Customer Service
    participant Disp as Disputes Team
    participant Scheme as Scheme Portal
    participant Merch as Acquirer/Merchant

    Cust->>CS: "I don't recognize this charge"
    CS->>CS: Log ticket — no link to txn ID
    CS->>Disp: Email screenshot weekly batch
    Disp->>Disp: Manual lookup in processor UI
    Disp->>Cust: Provisional credit (inconsistent policy)
    Disp->>Scheme: Chargeback filed — sometimes late
    Scheme->>Merch: Representment window starts
    Merch-->>Scheme: Compelling evidence
    Note over Disp: Missed deadline — loss absorbed
```

## Pain Points

| ID | Issue | Cost Driver |
|----|-------|-------------|
| PP-F01 | CS cannot see fraud score at contact | Wrong provisional credit decisions |
| PP-F02 | Chargeback deadlines tracked in spreadsheet | 12% missed filing window |
| PP-F03 | No unified case ID across CS and Disputes | Customer repeat contacts |
| PP-F04 | Representment evidence gathered manually | Low win rate (38%) |

## Root Cause — Missed Deadlines

Disputes team receives incomplete txn data from CS → rework delays filing past **120-day** issuer window for many fraud reason codes.
