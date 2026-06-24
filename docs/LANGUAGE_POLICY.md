# Language Policy

The CEO may write requests in any language.

OfficeCorp.ai documentation stays in English so the framework remains easy to share, inspect, and maintain. That does not limit the CEO's interaction language.

## Core Rule

The CEO's language is the default output language.

OfficeCorp.ai must:

- detect the CEO's language automatically
- understand intent, not just wording
- use English documentation, policies, agents, and skills internally
- answer in the same language as the CEO unless another output language is explicitly requested
- preserve technical names, file names, commands, code identifiers, and agent names in their original form when useful
- never require the CEO to translate a request before work can begin

## Language Layers

## Internal Operating Language

English is the default language for:

- documentation
- agent profiles
- policies
- prompts
- templates
- config examples

## CEO Interaction Language

The CEO may speak naturally in any language.

If the CEO writes in French, answer in French. If the CEO writes in English, answer in English. If the CEO writes in French but asks for English output, answer in English.

## Mixed-Language Requests

When a request uses multiple languages:

- follow any explicit output-language instruction
- otherwise use the dominant language of the CEO's request
- preserve technical terms in their original language when translating them would reduce clarity

## CEO Intent Over Syntax

The CEO does not need to know which employee, department, skill, or workflow is required.

The CEO expresses a need. OfficeCorp.ai translates that need into internal routing, employee selection, and final output.

Direct agent calls are still supported, but they are optional.

## Example

CEO:

```txt
Je veux ameliorer la documentation du projet pour qu'un assistant IA comprenne mieux comment router les agents.
```

OfficeCorp:

```txt
Recommandation: ajouter une politique de routage claire et un exemple de demande complete.

Equipe:
- Jared: coordination
- Peter: structure de connaissance
- Emily: documentation
- Keith: compression

Prochaine action: mettre a jour `docs/OPERATING_MODEL.md` et `routing/TASK_ROUTER.md`.
```
