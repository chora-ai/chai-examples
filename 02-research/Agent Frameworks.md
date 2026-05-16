---
type: research
status: active
description: Patterns and principles for building local-first, privacy-preserving infrastructure.
tags:
  - privacy
  - self-hosting
  - infrastructure
---

## Related Projects

- [[01-projects/AI Assistant|AI Assistant]] — the assistant must be privacy-preserving; model provider trust and credential handling are key concerns

## Related Research

- NA

---

## Propagated Insights

- When multiple independent agent frameworks (OpenClaw, IronClaw, Claude Code, Codex) converge on the same workspace structure — persistent memory, behavioral instructions, user context — it suggests a stable pattern rather than coincidence ([[00-daily/2026-03-26|2026-03-26]])

---

# Agent Frameworks

## Guiding Principles

### Local-First

Data stays on personally owned hardware by default. Cloud services are opt-in. This applies to:

- Model inference (Ollama, vLLM on local hardware)
- Version control / file syncing (git, Syncthing)

### Credential Isolation

Secrets should never be accessible to systems that process natural language. The attack surface for prompt injection grows with every credential visible to the LLM.

The ideal architecture encrypts credentials at rest and injects them at the host boundary — after the LLM has finished processing.
