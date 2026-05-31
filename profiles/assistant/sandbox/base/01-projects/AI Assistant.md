---
type: project
status: exploring
role: owner
description: Personal AI assistant — local-first, privacy-preserving, accessible via messaging.
tags:
  - ai
  - agents
  - privacy
---

# AI Assistant

## Sentiment

This feels like the convergence point for several threads — agentic systems research, privacy-first infrastructure, self-hosting. The question isn't whether to build this, but which path to take: extend something I've already started, adopt an existing framework, or combine the two.

## Action Items

- [ ] Define MVP scope — what is the simplest useful version?
- [ ] Decide approach: adopt Chai, adopt IronClaw, or hybrid
- [ ] Set up a messaging channel (Signal, Telegram, or Matrix)
- [ ] Test knowledge base operations through the chosen framework

## Sub-Notes

- NA

## External Links

- https://github.com/chora-ai/chai
- https://github.com/nearai/ironclaw
- https://github.com/openclaw/openclaw

---

## Framework Comparison

Three candidates for the assistant's foundation:

| | Chai | IronClaw | OpenClaw |
|---|---|---|---|
| **Language** | Rust | Rust | TypeScript |
| **Security** | Allowlisted execution, Ed25519 device pairing | WASM sandbox, credential vault, leak detection | App-level only; known vulnerabilities |
| **Messaging** | Telegram, Matrix, Signal | CLI, web, Signal, Telegram, Slack | 13+ channels incl. Signal |
| **Models** | Ollama, LM Studio, vLLM, HF, NIM, OpenAI | Any OpenAI-compat, Ollama, OpenRouter | Claude, OpenAI, Ollama |
| **Skills** | SKILL.md + tools.json (denied by default) | SKILL.md + ClawHub registry + WASM tools | Community marketplace (open by default) |
| **Memory** | In-memory sessions | Persistent workspace (libSQL, hybrid search) | Plugin-dependent |

**Chai** is the most controlled — built from scratch, specification-driven, every capability explicitly allowlisted. The gap: no sandboxing, no persistent memory, fewer integrations.

**IronClaw** is the most values-aligned alternative — Rust, privacy-first, WASM sandboxing, credential vault, persistent memory. Ships many capabilities Chai would need to build. The tradeoff: building on someone else's architecture.

**OpenClaw** has the most features and the weakest security — 430k+ lines of TypeScript, supply chain attacks (ClawHavoc), credentials exposed to the LLM. Useful as a reference, not a candidate for adoption.
