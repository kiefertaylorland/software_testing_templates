# Test Plan Template

> **How to use this file:** Copy it once per branch, PR, or repo under audit (e.g. `test-plan-<branch-name>.md`). Fill in every field. Do not change the category list, column headers, or the reference tables (§2–§4) — those must stay identical across every copy so filled copies are diffable against each other. This is the audit/scoring layer: it answers *"what testing exists and is it good enough?"* per category. For individual executable test steps, use the companion `test-case-template.md`, cross-referenced by the same identity block below.

---

## Identity

**Repo:** … · **Branch / PR:** … · **Commit ref:** …
**Auditor:** … · **Audit date:** … · **Sign-off:** QA Lead + Engineering or Product Lead
**Companion test case file:** `test-cases-<branch-name>.md`

---

## 0. Applicability Check

Classify the product/branch before scoring anything below:

- **High-risk** — touches employee PII, pay, identity, or health-adjacent data; multi-team; or in SOC 2 scope.
- **Standard** — single-team internal tooling with no sensitive row-level data.

**Classification for this branch:** ☐ High-risk ☐ Standard
**Reasoning:** …

---

## 1. How To Use This

1. **Measure.** Fill the blank template (§5) from actual tool output for the branch/PR/repo in question — not from memory or assumption.
2. **Score.** Apply the rubric (§2) and the status definitions (§3) to assign Invest / Keep / Hold / Drop per category.
3. **Name the trigger and the owner.** Every Hold and Drop gets a one-line revisit trigger *and a named owner*.

Two measurement rules that apply to every filled copy of this template:

- **Coverage signals are not comparable across categories.** "Coverage signal" means the most meaningful metric for that category. Never average or roll up across rows. 83% in E2E is not worse than 93.5% in Unit.
- **Measured ≠ enforced.** A number that exists on demand but gates nothing is a different risk profile than a CI-enforced threshold. Say which one you have in the CI Gate column — don't just record the number.

---

## 2. Decision Rubric

| Factor | What it means |
| --- | --- |
| **Data sensitivity & compliance exposure** | Does this branch touch PII, pay, identity, or other data in compliance scope? |
| **User-facing blast radius** | How many people notice if this breaks, and how publicly? |
| **Cost to instrument vs. cost of the failure** | Needs to be justified against a real scale number, not a hypothetical one. |
| **Team size reality** | A single QA engineer cannot carry a maximal matrix. |

---

## 3. Priority Definitions

| Priority | Definition |
| --- | --- |
| **Invest** | Tooling exists and is CI-gated. Scale or harden it. |
| **Keep** | Tooling exists and is adequate. Maintain current state. |
| **Hold** | Tooling exists but is partial or narrow, or consolidation work is pending. Hold items with active remediation work must have a named tracker entry (issue/ticket), a revisit trigger, and an owner. |
| **Drop** | No tooling and none planned until the trigger fires. Requires a revisit trigger and owner. Before marking a category Drop, record its current state in the audit record alongside the sign-off. |

---

## 4. Universal Defaults

These are the floor — do not mark all four Drop without an explicit, named exception approved at sign-off:

- **Unit** — cheapest signal per test written.
- **Security — Access Control & Data Boundaries** — RLS-equivalent enforcement.
- **Smoke** — cheap, catches the worst regressions before they ship.
- **Regression** — unit/E2E run on a cadence.

---

## 5. The Template

For every row: fill **Tooling & pipeline ref**, **Coverage signal**, and **CI gate** from actual observed state (run the tool, read the pipeline config — don't estimate). Then apply §2/§3 to set **Priority**. Every **Hold** or **Drop** row must have an **Owner** and a **Revisit trigger** filled in; leaving either blank is not a valid Hold/Drop. For **Hold** rows with active remediation, also add the tracker entry in the Notes row beneath the table. For **Drop** rows, add the "current state at Drop" note in the same place.

| Category | Tooling & pipeline ref | Coverage signal | CI gate | Priority | Owner | Revisit trigger (Hold & Drop) |
| --- | --- | --- | --- | --- | --- | --- |
| Unit | | | | | | |
| Integration | | | | | | |
| Integration — Third-Party Data Handling | | | | | | |
| System / E2E | | | | | | |
| Smoke | | | | | | |
| API / Interface | | | | | | |
| Regression | | | | | | |
| Mutation | | | | | | |
| Security — Access Control & Data Boundaries | | | | | | |
| Security — Vulnerability Scanning | | | | | | |
| Performance | | | | | | |
| Load | | | | | | |
| Stress | | | | | | |
| Reliability | | | | | | |
| Compatibility | | | | | | |
| Accessibility | | | | | | |
| Usability | | | | | | |
| Globalization | | | | | | |
| Localization | | | | | | |
| Exploratory | | | | | | |

### Hold / Drop notes (tracker entries & current-state records)

| Category | Status | Tracker entry (issue/ticket, Hold only) | Current state at time of Drop (Drop only) |
| --- | --- | --- | --- |
| | | | |

---

## Sign-off

| Role | Name | Date | Approved |
| --- | --- | --- | --- |
| QA Lead | | | ☐ |
| Engineering or Product Lead | | | ☐ |
