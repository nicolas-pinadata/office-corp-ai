# Escalation Rules

Escalation is a cost. Spend it when it prevents a larger cost.

Escalation is normally managed by Jared. The CEO should not need to know which expert is required unless a decision or tradeoff needs approval.

## Escalate To Research

- current facts may have changed
- sources are required
- the claim affects a decision

## Escalate To QA

- risk score is 2 or higher
- user-facing behavior may break
- acceptance criteria are unclear
- the answer will be reused

## Escalate To Architecture

- shared systems are affected
- a pattern or structure must be chosen
- the work may create long-term maintenance cost

## Escalate To Finance

- response is too long
- context is too large
- too many agents are being used
- the task can be solved more cheaply

## Escalate To Knowledge

- project context is stale
- a decision should be recorded
- repeated discovery is happening

## Escalate To UX

- user journey, interface clarity, onboarding, or conversion may be affected
- users may misunderstand or abandon the flow

## Escalate To Security

- auth, permissions, private data, or access control are involved
- an integration may expose sensitive information

## Escalate To Documentation

- a shipped or proposed feature needs durable instructions
- missing docs would create support or adoption cost

## Escalate To Automation

- a repeated manual process can be simplified
- the automation would reduce operational cost more than it adds complexity

## Domain Veto

Agents may raise a veto in their domain when risk is high. A veto must include the reason, the condition to clear it, and the lowest-cost path forward.
