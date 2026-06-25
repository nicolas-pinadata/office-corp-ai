# Token Economics

OfficeCorp.ai treats tokens as company money.

Token savings must not remove the details needed to understand, verify, or act. OfficeCorp uses smart compression, not blind shortening.

## Cost Categories

- **Prompt cost**: instructions, context, examples, and history.
- **Work cost**: reasoning, tool calls, research, and agent coordination.
- **Output cost**: final answer length.
- **Maintenance cost**: future confusion caused by bloated or unclear answers.

## Budget Modes

- **Lean**: shortest complete answer. Default for simple tasks.
- **Standard**: balanced detail and brevity. Default for normal work.
- **Deep Work**: higher spend allowed for complex, risky, or ambiguous tasks.
- **Audit**: spend tokens to reduce future cost or risk.

## Output Standards By Budget

## Lean

- direct answer
- maximum one short justification
- one next action only if useful

## Standard

- recommendation
- short reasoning
- concrete steps
- risks when relevant
- compact work receipt when routing or validation matters

## Deep Work

- diagnosis
- options
- recommendation
- plan
- risks
- validation
- work receipt with agent contribution delta

## Audit

- waste found
- missing information
- what should be compressed
- optimized version
- remaining risk
- whether multi-agent routing created enough value to justify its cost

## Communication Compression

Use the shortest mode that preserves quality:

- **Normal**: strategy and major decisions.
- **Concise**: default CEO-facing mode.
- **Compressed**: routine updates and low-risk work.
- **Executive**: decision-only output.
- **Inter-Agent**: internal handoffs.

See [COMMUNICATION_MODES.md](COMMUNICATION_MODES.md).

## CFO Questions

- Can one employee do this?
- Can old context be summarized or removed?
- Is this source required?
- Is QA justified by risk?
- Can the final answer be half as long?
- Does this paragraph change the CEO's decision?
- Did each extra agent change quality, risk, cost, speed, or clarity?
- Would a default LLM answer have produced the same result with fewer tokens?
