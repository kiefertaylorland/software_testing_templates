# Test Case Template

> **How to use this file:** Copy it once per branch, PR, or repo under audit (e.g. `test-cases-<branch-name>.md`), alongside a filled `test-plan-<branch-name>.md`. This is the execution layer: individual, runnable test cases that back up the category-level scores in the Test Plan. One row per test case, grouped under a `##` heading per category, in the same order as the Test Plan's §5 table — this keeps the two documents skimmable side by side. Do not add categories beyond the legend below; if a case doesn't fit one of these, it belongs in Exploratory.

---

## Identity

**Repo:** … · **Branch / PR:** … · **Commit ref:** …
**Tester:** … · **Date executed:** … · **Sign-off:** QA Lead + Engineering or Product Lead
**Companion test plan file:** `test-plan-<branch-name>.md`

---

## Category legend

Every `Category` value below must be exactly one of these (must match the Test Plan's row names):

Unit · Integration · Integration — Third-Party Data Handling · System / E2E · Smoke · API / Interface · Regression · Mutation · Security — Access Control & Data Boundaries · Security — Vulnerability Scanning · Performance · Load · Stress · Reliability · Compatibility · Accessibility · Usability · Globalization · Localization · Exploratory

## Field reference

| Field | Meaning |
| --- | --- |
| Test Case ID | Short code: `<CATEGORY-PREFIX>-<seq>`, e.g. `SEC-AC-001`, `UNIT-014`. Prefixes are free-form but must stay consistent within a file. |
| Category | One value from the legend above. |
| Title / Objective | One line: what this case proves. |
| Preconditions | State the system/data must be in before running the steps. |
| Test Steps | Numbered, concrete, reproducible by someone unfamiliar with the change. |
| Test Data | Exact inputs used (or a pointer to a fixture/seed script). |
| Expected Result | What "pass" looks like, stated before running the case. |
| Actual Result | What actually happened. |
| Status | Pass / Fail / Blocked / N/A |
| Severity | Critical / High / Medium / Low — required if Status = Fail. |
| Security or Compliance Flag | Y/N + one-line note. Flag Y whenever the case touches PII, pay, identity data, access control, or a compliance control — even if the category isn't a Security row. |
| Evidence | Link or path to log output, screenshot, scan report, or CI run. |

## Worked examples (illustrative only — replace with real cases; do not leave these in a filled copy)

| Test Case ID | Category | Title / Objective | Preconditions | Test Steps | Test Data | Expected Result | Actual Result | Status | Severity | Security/Compliance Flag | Evidence |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| EX-IMPL-001 | System / E2E | New checkout flow completes for a standard user | Test account with valid payment method exists | 1. Log in as test user 2. Add item to cart 3. Complete checkout | Test account `qa-user-01`, test card `4242…` | Order is created and confirmation screen shows order ID | Order created, confirmation shown with order ID `ord_123` | Pass | — | N | `evidence/checkout-e2e-run-42.mp4` |
| EX-SEC-001 | Security — Access Control & Data Boundaries | User A cannot read User B's profile via direct object reference | Two distinct user accounts (A, B) exist with no shared org | 1. Log in as User A 2. Note User B's profile ID 3. Request `/api/users/{B_id}/profile` directly | User A session token, User B's ID | 403/404 — request denied, no profile data returned | Request returned 200 with User B's full profile | Fail | Critical | Y — cross-tenant PII exposure | `evidence/idor-repro-2026-08-25.har` |

---

## Test cases by category

### Unit

| Test Case ID | Title / Objective | Preconditions | Test Steps | Test Data | Expected Result | Actual Result | Status | Severity | Security/Compliance Flag | Evidence |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| | | | | | | | | | | |

### Integration

| Test Case ID | Title / Objective | Preconditions | Test Steps | Test Data | Expected Result | Actual Result | Status | Severity | Security/Compliance Flag | Evidence |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| | | | | | | | | | | |

### Integration — Third-Party Data Handling

| Test Case ID | Title / Objective | Preconditions | Test Steps | Test Data | Expected Result | Actual Result | Status | Severity | Security/Compliance Flag | Evidence |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| | | | | | | | | | | |

### System / E2E

| Test Case ID | Title / Objective | Preconditions | Test Steps | Test Data | Expected Result | Actual Result | Status | Severity | Security/Compliance Flag | Evidence |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| | | | | | | | | | | |

### Smoke

| Test Case ID | Title / Objective | Preconditions | Test Steps | Test Data | Expected Result | Actual Result | Status | Severity | Security/Compliance Flag | Evidence |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| | | | | | | | | | | |

### API / Interface

| Test Case ID | Title / Objective | Preconditions | Test Steps | Test Data | Expected Result | Actual Result | Status | Severity | Security/Compliance Flag | Evidence |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| | | | | | | | | | | |

### Regression

| Test Case ID | Title / Objective | Preconditions | Test Steps | Test Data | Expected Result | Actual Result | Status | Severity | Security/Compliance Flag | Evidence |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| | | | | | | | | | | |

### Mutation

| Test Case ID | Title / Objective | Preconditions | Test Steps | Test Data | Expected Result | Actual Result | Status | Severity | Security/Compliance Flag | Evidence |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| | | | | | | | | | | |

### Security — Access Control & Data Boundaries

| Test Case ID | Title / Objective | Preconditions | Test Steps | Test Data | Expected Result | Actual Result | Status | Severity | Security/Compliance Flag | Evidence |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| | | | | | | | | | | |

### Security — Vulnerability Scanning

| Test Case ID | Title / Objective | Preconditions | Test Steps | Test Data | Expected Result | Actual Result | Status | Severity | Security/Compliance Flag | Evidence |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| | | | | | | | | | | |

### Performance

| Test Case ID | Title / Objective | Preconditions | Test Steps | Test Data | Expected Result | Actual Result | Status | Severity | Security/Compliance Flag | Evidence |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| | | | | | | | | | | |

### Load

| Test Case ID | Title / Objective | Preconditions | Test Steps | Test Data | Expected Result | Actual Result | Status | Severity | Security/Compliance Flag | Evidence |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| | | | | | | | | | | |

### Stress

| Test Case ID | Title / Objective | Preconditions | Test Steps | Test Data | Expected Result | Actual Result | Status | Severity | Security/Compliance Flag | Evidence |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| | | | | | | | | | | |

### Reliability

| Test Case ID | Title / Objective | Preconditions | Test Steps | Test Data | Expected Result | Actual Result | Status | Severity | Security/Compliance Flag | Evidence |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| | | | | | | | | | | |

### Compatibility

| Test Case ID | Title / Objective | Preconditions | Test Steps | Test Data | Expected Result | Actual Result | Status | Severity | Security/Compliance Flag | Evidence |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| | | | | | | | | | | |

### Accessibility

| Test Case ID | Title / Objective | Preconditions | Test Steps | Test Data | Expected Result | Actual Result | Status | Severity | Security/Compliance Flag | Evidence |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| | | | | | | | | | | |

### Usability

| Test Case ID | Title / Objective | Preconditions | Test Steps | Test Data | Expected Result | Actual Result | Status | Severity | Security/Compliance Flag | Evidence |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| | | | | | | | | | | |

### Globalization

| Test Case ID | Title / Objective | Preconditions | Test Steps | Test Data | Expected Result | Actual Result | Status | Severity | Security/Compliance Flag | Evidence |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| | | | | | | | | | | |

### Localization

| Test Case ID | Title / Objective | Preconditions | Test Steps | Test Data | Expected Result | Actual Result | Status | Severity | Security/Compliance Flag | Evidence |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| | | | | | | | | | | |

### Exploratory

| Test Case ID | Title / Objective | Preconditions | Test Steps | Test Data | Expected Result | Actual Result | Status | Severity | Security/Compliance Flag | Evidence |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| | | | | | | | | | | |

---

## Sign-off

| Role | Name | Date | Approved |
| --- | --- | --- | --- |
| QA Lead | | | ☐ |
| Engineering or Product Lead | | | ☐ |
