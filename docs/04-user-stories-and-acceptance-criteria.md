# User Stories — Fraud & Chargebacks

### US-DISP-01 — Create dispute from customer contact

**As a** customer service agent  
**I want** to open a dispute from the transaction detail screen  
**So that** all txn context flows to the disputes team automatically

- Required fields: dispute type, customer statement, contact channel.
- Case ID returned and communicated to customer.

---

### US-DISP-02 — Auto provisional credit

```gherkin
  Scenario: Eligible fraud dispute under threshold
    Given transaction amount is 120 EUR
    And dispute type is FRAUD_CNP
    And transaction age is 14 days
    When case is submitted
    Then provisional credit is posted within 1 hour
    And customer notification is sent
```

---

### US-CB-01 — Deadline alerts

**As a** disputes analyst  
**I want** escalating alerts before scheme deadlines  
**So that** I never miss a filing window

---

### US-CB-02 — Representment evidence pack

**As a** disputes analyst  
**I want** a checklist of evidence for reason code 10.4  
**So that** I can accept or challenge merchant representment quickly

| Evidence Item | Required for 10.4 defend |
|---------------|--------------------------|
| 3DS authentication log | If liability shift |
| AVS/CVV match result | Yes |
| Prior undisputed txns at merchant | Optional |

---

### US-FRAUD-01 — CS fraud context

**As a** CS agent  
**I want** to see fraud score and rule hits on a transaction  
**So that** I can set customer expectations on dispute outcome
