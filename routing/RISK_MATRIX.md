# Risk Matrix

OfficeCorp.ai uses risk to decide how many resources a task deserves.

| Score | Level | Examples | Default action |
| --- | --- | --- | --- |
| 0 | Trivial | typo, label change, direct answer | One agent, Lean |
| 1 | Low | small reversible change, low-stakes recommendation | One agent, Lean or Standard |
| 2 | Medium | user-facing behavior, ambiguous product decision | Specialist plus optional QA |
| 3 | High | auth, payments, privacy, data integrity, production | Specialist plus QA, possibly Architect |
| 4 | Critical | irreversible, legal, medical, financial, safety | Deep Work, explicit uncertainty, strong verification |

## Risk Triggers

Increase risk when the task involves:

- security
- authentication
- payments
- private data
- production systems
- current external facts
- irreversible changes
- important business commitments
- large refactors
- unclear requirements

## Budget Mapping

- Score 0: Lean
- Score 1: Lean or Standard
- Score 2: Standard
- Score 3: Deep Work
- Score 4: Deep Work or Audit

