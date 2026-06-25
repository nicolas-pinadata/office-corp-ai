# Provider Architecture

OfficeCorp is LLM-agnostic by design.

OfficeCorp is the company. Language models, tools, files, browsers, APIs, and interfaces are resources the company may use. Business logic belongs to OfficeCorp governance, workflows, playbooks, decision frameworks, and organizational memory. It must not be embedded in a specific model, chat product, coding agent, or runtime.

Guiding principles:

- OfficeCorp owns the reasoning. LLMs provide intelligence.
- OfficeCorp is designed around stable business processes, not around a specific AI provider.
- The user interacts with OfficeCorp, not with a model vendor.
- Providers supply capabilities. They do not define company policy.
- The default implementation is local files and Markdown.

## Provider Boundary

A provider is an interchangeable capability boundary.

OfficeCorp documents what it needs from a capability, but the rest of the company should not depend on how that capability is implemented. A future interface, model, storage system, or external service should be able to replace a provider without changing OfficeCorp governance or workflows.

## Core Providers

## Workspace Provider

The Workspace Provider identifies the active workspace and exposes its structured business knowledge.

Default implementation:

- local `workspaces/` folder;
- one folder per business, startup, SaaS, client, or product;
- Markdown documentation organized by domain.

OfficeCorp depends on:

- active workspace identity;
- readable workspace documentation;
- workspace-level decisions and current state;
- clear boundaries between workspaces.

OfficeCorp must not depend on:

- a specific folder location beyond the configured default;
- a specific editor;
- a specific repository host;
- a specific runtime.

## Knowledge Provider

The Knowledge Provider supplies relevant organizational knowledge for a task.

Default implementation:

- local Markdown documents;
- workspace folders such as `docs/`, `research/`, `roadmap/`, `architecture/`, `ux/`, `product/`, `marketing/`, `decisions/`;
- OfficeCorp governance documents in this repository.

OfficeCorp depends on:

- retrieving relevant knowledge by workspace and domain;
- preserving source boundaries;
- distinguishing durable knowledge from temporary conversation context;
- respecting source authority.

OfficeCorp must not depend on a specific retrieval technology.

## Memory Provider

The Memory Provider preserves institutional knowledge that should survive a single session.

Default implementation:

- decision records in Markdown;
- current-state documents;
- lessons learned;
- reusable playbooks;
- compact summaries of durable context.

OfficeCorp depends on:

- durable decisions being available before new recommendations;
- stale or obsolete memory being pruned;
- meaningful lessons being captured when future work will benefit.

OfficeCorp must not treat raw chat history as the primary memory system.

## LLM Provider

The LLM Provider supplies language-model intelligence for analysis, drafting, classification, synthesis, and reasoning support.

Examples include ChatGPT, Codex, Claude, Gemini, and local models.

OfficeCorp depends on:

- receiving a task and relevant context;
- producing a response that follows OfficeCorp governance;
- disclosing uncertainty when confidence is not evidence;
- using tools only within the applicable provider permissions.

OfficeCorp must not depend on:

- model-specific hidden behavior;
- proprietary prompt conventions;
- provider-specific tool names;
- vendor-specific memory;
- one model's training data as an authority layer.

## Interface Provider

The Interface Provider is the surface through which the user interacts with OfficeCorp.

Examples include chat, coding agents, editors, browser-based tools, documentation workflows, and manual workflows.

OfficeCorp depends on:

- receiving user intent;
- returning a final answer;
- asking for approval when a business or safety decision requires it;
- making work observable when complexity justifies it.

OfficeCorp must not require a specific interface for the operating model to remain valid.

## Provider Rules

- Provider implementations may change; OfficeCorp governance should remain stable.
- Providers should expose capabilities in plain terms.
- Agents should request capabilities, not vendor-specific implementation details.
- Provider-specific behavior belongs in adapter documentation, not in company governance.
- If provider capability is missing, OfficeCorp should degrade gracefully and state the limitation.

## Current Default

Today, OfficeCorp is a readable, file-based framework.

The default provider stack is:

```txt
Interface Provider: user prompt or manual workflow
LLM Provider: whichever model is running OfficeCorp
Workspace Provider: local filesystem
Knowledge Provider: Markdown documentation
Memory Provider: Markdown decision records and current-state files
```

This keeps the architecture extensible without introducing unnecessary runtime complexity.
