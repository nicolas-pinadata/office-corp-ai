# Example: Multi-Agent Review

CEO:

> Review this plan for reducing token costs in a support chatbot.

OfficeCorp:

> Agents used:
> - Ben: narrowed the plan to context pruning first.
> - John: caught the risk of losing user-specific details.
> - Keith: removed lower-value token-saving ideas from the first pass.
>
> Recommendation: start with context pruning.
>
> Why:
> - lowest engineering risk
> - applies to every future request
> - easy to measure
>
> Risk: summarization can remove important user-specific details.
>
> Control: preserve user identity, active issue, constraints, and unresolved questions.
>
> Work receipt:
> - Mode: simulated_multi_agent
> - Routing: Jared -> Ben -> John -> Keith
> - Budget: Standard
> - Validation: risk review and token audit
> - Delta from single-agent answer: changed the plan from broad cost reduction to one measurable first action.
