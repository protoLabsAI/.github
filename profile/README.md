![protoLabs.studio](https://raw.githubusercontent.com/protoLabsAI/.github/main/profile/assets/readme-banner.png)

# protoLabs.studio

**We build systems that build themselves.** An indie studio running experiments in the open — and sharing the patterns that build them.

It's one person and a fleet of agents shipping the work. We build games, simulators, and specialized agents on top of infrastructure we run ourselves, from the hardware up. The patterns that fall out of building them (orchestration, voice-as-code, release automation) get open-sourced as we go, for anyone who wants to read them and build their own.

## Patterns you can take

Infrastructure we ship as patterns to study and steal, not products you wait on us to improve.

- [`release-tools`](https://github.com/protoLabsAI/release-tools) — release-notes generator and Discord embed as one GitHub Action. Runs on every repo here.
- [`rabbit-hole.io`](https://github.com/protoLabsAI/rabbit-hole.io) — research agent that turns a topic and a budget into a knowledge graph instead of a pile of links.
- [`protoCLI`](https://github.com/protoLabsAI/protoCLI) — an AI agent that lives in your terminal.
- [`protoBanana`](https://github.com/protoLabsAI/protoBanana) — chat-native image generation and editing, served as an OpenAI-compatible provider on top of ComfyUI.
- [`protoWorkstacean`](https://github.com/protoLabsAI/protoWorkstacean) — a pluggable pubsub bus for agentic action.

## The engine

[`protoAgent`](https://github.com/protoLabsAI/protoAgent) is the adaptable engine: a lean, A2A-native agent on LangGraph that ships a small core and grows at runtime instead of by forking. Capability arrives three ways — **plugins** install from a git URL (tools, subagents, MCP servers, console views), **skills** load on demand as the model needs them, and **delegate agents** route work out over A2A, the OpenAI-compatible API, or ACP, so it can spawn other coding agents (protoCLI, Claude Code) as subprocesses. Run one agent or orchestrate a fleet; drive it from the console, the API, or A2A. The boring parts — A2A spec handling, cost and extension emission, tracing, the release pipeline — stay stable across every agent, so forking is close to a rewrite of `SOUL.md` and a couple of files, not inheriting a pile.

## What runs it

The substrate the experiments sit on. Most of it stays private; the parts worth sharing surface as the repos above.

- **protoLab** — LLM eval, training, and inference on 2× RTX PRO 6000 Blackwell (192 GB). LiteLLM gateway, Langfuse, vLLM.
- **mythxengine-sdk** — deterministic multi-agent worlds in Rust. Genre-agnostic; games plug in as packs.
- **homelab-iac** — the self-hosted Proxmox cluster it all runs on, behind Caddy, Cloudflare, and Tailscale.

## What we build with it

- **[ORBIS](https://orbis.protolabs.studio)** — a voice-first AI companion: an orb that talks, remembers you, and routes the heavy lifting to your agents. Live.
- **[MythXEngine](https://mythxengine.com)** — a TTRPG world-and-story generator on mythxengine-sdk. Generate a world, then play it.
- **PilotProtocol** — mech-vs-mech agents fighting on a hex grid, with a click-through replay viewer that shows each model's reasoning a move at a time.

## How it works

```
idea → decision record → task graph → agent picks it up → worktree
isolation → implementation → antagonistic review → CI → PR → merge
```

Every transition is a gate. Work that fails one goes back a step or escalates to a stronger model, and nothing merges that didn't pass the same checks a person would.

## By the numbers

Rough aggregates across the protoLabsAI org, from GitHub (May 2026):

| | |
|---|---|
| Repositories | 82 (26 public, open to fork) |
| Merged pull requests | 6,795 |
| Stack | TypeScript · Python · Rust |
| Operator contributions, last 12 months | ~14,000 |

One person and a fleet of agents. We keep the numbers visible because a claim without one is just marketing.

## Where to find us

- [**protolabs.studio**](https://protolabs.studio) — home and blog
- [**hello@protolabs.consulting**](mailto:hello@protolabs.consulting) — consulting: pattern transfer, not retainer work
- [**@protoLabsAI**](https://x.com/protoLabsAI) — X
- [**Substack**](https://substack.com/@protolabsai) — long-form

---

**MIT licensed. No subscriptions, no microtransactions, no gated tiers** — pay-what-you-want and donations only. The infrastructure ships as patterns to study and steal. Bring your own hacking.
