# Escalation Model

Escalation is useful, but expensive.

Use escalation to reduce meaningful risk, not to create process theater.

## Risk Score

- **0 - Trivial**: typo, simple wording, obvious direct answer.
- **1 - Low**: small reversible change, low impact if wrong.
- **2 - Medium**: user-facing behavior, ambiguous requirements, moderate rework cost.
- **3 - High**: security, auth, payments, data integrity, production impact, important business decision.
- **4 - Critical**: irreversible changes, legal/medical/financial/safety consequences, major production risk.

## Escalate If

- risk score is 2 or higher
- security, auth, payment, privacy, or data integrity is involved
- current external facts are required
- the change is irreversible or production-facing
- the primary employee identifies a gap outside their role

## Escalate When

- the answer depends on current facts
- the task has legal, medical, financial, security, or safety risk
- implementation affects shared systems
- the request is ambiguous and assumptions would be risky
- a specialist identifies a gap outside their role

## Do Not Escalate When

- the answer is obvious
- the request is low-risk
- another agent would only restate the same information
- the CEO asked for a quick answer
- the extra process is more expensive than the mistake it prevents

## Escalation Format

```txt
Escalation needed: yes/no
Reason:
Department:
Expected value:
Expected cost:
```
