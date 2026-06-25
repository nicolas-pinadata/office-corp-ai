# Organizational Memory

OfficeCorp thinks in terms of organizational knowledge, not individual chat history.

Chat history is temporary working context. Organizational memory is durable company knowledge that future employees can inspect, reuse, challenge, and update.

## Knowledge Domains

Workspace knowledge should be organized by business domain:

- product documentation;
- research;
- architecture;
- UX;
- roadmap;
- business strategy;
- marketing;
- decisions;
- lessons learned;
- operating procedures;
- reusable playbooks.

The exact folder structure may vary by workspace, but the knowledge should remain understandable to a human and portable across tools.

## Memory Responsibilities

OfficeCorp should preserve:

- durable decisions;
- validated facts that will affect future work;
- known risks and constraints;
- rejected alternatives when they explain current direction;
- lessons learned from launches, QA, incidents, customer feedback, or research;
- reusable operating procedures.

OfficeCorp should not preserve:

- raw conversation logs as the main knowledge source;
- stale assumptions;
- duplicate summaries;
- rejected ideas after the reason has been captured;
- temporary implementation notes that will not matter later.

## Decision Records

Important decisions should be recorded in a structured decision record.

Each decision should contain:

- date;
- workspace;
- decision;
- context;
- alternatives considered;
- final choice;
- rationale;
- risks;
- expected impact.

Recommended format:

```md
# Decision: {short title}

Date: YYYY-MM-DD
Workspace: {workspace-name}

## Decision

{What was decided.}

## Context

{Why the decision was needed.}

## Alternatives Considered

- {Option A}
- {Option B}
- {Option C}

## Final Choice

{Chosen option.}

## Rationale

{Why this option was selected.}

## Risks

- {Risk}

## Expected Impact

{What should change because of this decision.}
```

## Consultation Rule

Before proposing a new decision, employees should consult relevant previous decisions when available.

If a recommendation conflicts with a previous decision, OfficeCorp should:

1. identify the conflict;
2. explain what changed;
3. recommend whether to keep, amend, or supersede the older decision;
4. record the new decision if it materially changes direction.

## Knowledge Lifecycle

Organizational memory should be maintained deliberately:

- Capture when a decision, fact, risk, or lesson will matter again.
- Compress when a document grows too large to be useful.
- Prune when information becomes stale, duplicated, or misleading.
- Supersede instead of silently rewriting important history.
- Link related documents where it helps future employees find context.

## Ownership

Peter, Knowledge Manager, owns memory quality.

Emily, Documentation Specialist, owns clarity and durable documentation.

Domain owners own the correctness of knowledge in their area:

- Ben owns product knowledge.
- Carla owns architecture knowledge.
- Mia owns UX knowledge.
- Victor owns market and venture evidence.
- Laurie owns marketing knowledge.
- Ed owns financial and business analysis.
- John owns QA and validation records.
- Anton owns security-sensitive knowledge.

OfficeCorp should treat memory as institutional infrastructure, not as a transcript.
