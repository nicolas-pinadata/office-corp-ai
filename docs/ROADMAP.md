# Architecture Status

This document describes the current architecture areas represented in the repository. It should not be treated as a promise of future products, commercial offerings, or unimplemented services.

## Installable Core

- `.officecorp/` minimal template
- configuration schemas
- task router
- risk matrix
- token budget standards
- optional workspace memory files

## Standardized Delegation

- structured agent profiles
- department routing rules
- escalation rules
- output formats by budget mode
- behavioral examples

## Company Extensions

- optional playbooks
- optional project briefs
- optional decision logs
- rich context templates
- documentation for use with any AI assistant
- autonomous company initiatives
- communication modes
- multilingual CEO interaction
- observability standards for work receipts and decision traces

## AI Product Company Framework

- product company model
- idea intake process
- Challenge & Validation phase
- Investment Board governance
- portfolio management
- opportunity scoring
- product execution brief after `GO` or accepted `PIVOT`
- launch, growth, and iteration playbooks

## LLM-Agnostic Architecture

- provider architecture
- workspace model
- organizational memory
- decision records
- local files and Markdown as the default provider implementation
- independence from a specific runtime, AI tool, orchestration framework, or vendor

## Extension Boundary

OfficeCorp documents provider extension points without requiring those integrations to exist today. The core framework should remain stable when different interfaces, LLMs, workspace stores, knowledge sources, or memory providers are introduced.
