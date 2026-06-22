# BRD — Dispute & Chargeback Management Platform

| Project | CardGuard Disputes v1 |
|---------|----------------------|

## 1. Objectives

- Unified case from customer contact through chargeback resolution.
- Zero missed scheme filing deadlines for in-scope disputes.
- Representment win rate +10 percentage points via evidence checklist.

## 2. Provisional Credit Policy (BR-DISP-01)

| Condition | Provisional Credit |
|-----------|-------------------|
| Fraud claim + txn < 60 days + no 3DS liability shift | Auto PC up to €500 |
| Fraud claim + amount > €500 | Fraud ops approval within 4h |
| Non-fraud service dispute | No auto PC — merchant contact first |
| Customer history: 3+ disputes in 12mo | Manual review |

## 3. Chargeback Filing Rules (BR-CB-01)

| Step | SLA from case open |
|------|-------------------|
| Eligibility check (reason code mapping) | 1 business day |
| Scheme filing | ≤ 5 business days |
| Representment review | Within 2 days of receipt |
| Pre-arbitration decision | Per scheme calendar |

System SHALL alert at T-7, T-3, T-1 days before scheme deadline.

## 4. Functional Requirements

| ID | Requirement | Priority |
|----|-------------|----------|
| FR-01 | Create dispute case linked to `transactionId` | Must |
| FR-02 | Auto-map customer narrative to reason code candidates | Should |
| FR-03 | Track scheme deadlines per reason code | Must |
| FR-04 | Evidence checklist by reason code | Must |
| FR-05 | File chargeback via scheme API integration | Must |
| FR-06 | Provisional credit workflow with approval matrix | Must |
| FR-07 | Customer status portal (case timeline) | Should |
| FR-08 | Fraud score visible to CS (read-only) | Must |

## 5. Reporting

- Chargeback ratio by merchant category (monthly)
- Win/loss by reason code
- PC recovery rate after merchant representment
