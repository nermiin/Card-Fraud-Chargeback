# Worked Scenarios: Fraud & Chargebacks

Fictional cases on the issuer side. Rules refer to the [To-Be Process Design](07-to-be-process-design.md).

## S-01 CNP Fraud Under the Auto Credit Limit

| Date (2026) | Event | Detail |
|-------------|-------|--------|
| 3 March | Transaction processed | EUR 120.00, online, no 3DS |
| Monday 16 March | Customer reports fraud | Age 13 days, row 3 applies |
| 16 March | Provisional credit | EUR 120.00 within 1 hour, card blocked |
| Wednesday 18 March | Chargeback filed, code 10.4 | Within the 5 business day limit |
| Friday 17 April | Acquirer response due | 30 days after filing |
| 17 April | No response received | Chargeback final, credit made permanent |

**Filing deadline control** (had the case not been filed earlier):

| Control point | Date | Note |
|---------------|------|------|
| Last filing day (120 days) | Wednesday 1 July | |
| T-7 alert | Wednesday 24 June | |
| T-3 alert | Friday 26 June | Sunday 28 June moved to prior business day (BR-CB-02) |
| T-1 alert | Tuesday 30 June | |

## S-02 High-Value Fraud Claim

| Step | Detail |
|------|--------|
| Claim | EUR 1,450.00, CNP, 9 days old, no 3DS |
| Rule | Row 2, above EUR 500 |
| Fraud Ops | Reviews score and device history, approves in 2h 40m, within the 4h limit |
| Outcome | Full credit, because the limit routes the decision and does not cap the refund |

## S-03 3DS Authenticated Claim

| Step | Detail |
|------|--------|
| Claim | EUR 310.00, CNP, 3DS challenge passed |
| Rule | Row 4, manual review by the next business day |
| Investigation | New device enrolled two hours before the purchase, consistent with account takeover |
| Outcome | Refund to the customer. 3DS liability shift means code 10.4 is likely unavailable, so the loss stays with the issuer and is reported as authentication-failure fraud |

## S-04 Duplicate Charge

| Item | First | Second |
|------|-------|--------|
| Amount | EUR 89.90 | EUR 89.90 |
| Merchant | Same | Same |
| Date | 5 May | 5 May |
| Auth code | 714220 | 714220 |

Same authorization code and amount point to a true duplicate. The case maps to code 12.6 for the EUR 89.90 second charge. No fraud block is applied to the card.

## S-05 Representment Received

| Step | Detail |
|------|--------|
| Original | EUR 240.00 chargeback, code 10.4 |
| Representment | Merchant sends two prior transactions, dated 150 and 300 days before the disputed sale, with matching device ID and shipping address |
| Review | Evidence satisfies Compelling Evidence 3.0 |
| Decision | Accept within 2 days, reverse credit, notify customer in writing with a route to complain |

## S-06 Financial Impact

Illustrative month, in-scope disputes only, average value EUR 85.

| Driver | Calculation | Value (EUR) |
|--------|-------------|-------------|
| Missed filing at 12% | 2,000 cases x 12% = 240 x 85 | 20,400 |
| Filed cases | 2,000 - 240 = 1,760 | |
| Representments at 30% | 1,760 x 30% = 528 x 85 | 44,880 contested |
| Win rate +10 points | 44,880 x 10% | 4,488 |
| **Monthly benefit** | 20,400 + 4,488 | **24,888** |
| **Annual benefit** | 24,888 x 12 | **298,656** |

The 30% representment rate is an assumption, to be replaced with actual data from the first quarter.

## Edge Case Register

| ID | Situation | Expected Behavior | Rule |
|----|-----------|-------------------|------|
| E-01 | Fraud claim of exactly EUR 500.00 | Auto credit, limit is inclusive | Table row 3 |
| E-02 | Fraud claim on exactly day 60 | Manual review | Table row 5 |
| E-03 | Customer disputes a transaction already refunded by merchant | Case closed, no chargeback | BR-CB-01 eligibility |
| E-04 | Partial dispute, EUR 30 of EUR 100 | Chargeback for EUR 30 only | FR-05 |
| E-05 | Alert date on a public holiday | Moves to prior business day | BR-CB-02 |
| E-06 | Merchant refunds after chargeback is filed | Duplicate credit check, case reconciled | FR-06 |
