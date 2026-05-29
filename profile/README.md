![protoLabs.studio](https://raw.githubusercontent.com/protoLabsAI/.github/main/profile/assets/readme-banner.png)

# protoLabs.studio

**An AI-native indie studio with an open-source habit.** We build systems that build themselves.

We're two people and a fleet of agents that ships the work. We build games, simulators, and specialized agents on top of infrastructure we run ourselves, from the hardware up. The patterns that fall out of building them (orchestration, voice-as-code, release automation) get open-sourced as we go, for anyone who wants to read them and build their own.

## Patterns you can take

Infrastructure we ship as patterns to study and steal, not products you wait on us to improve.

- [`release-tools`](https://github.com/protoLabsAI/release-tools) — release-notes generator and Discord embed as one GitHub Action. Runs on every repo here.
- [`rabbit-hole.io`](https://github.com/protoLabsAI/rabbit-hole.io) — research agent that turns a topic and a budget into a knowledge graph instead of a pile of links.
- [`protoCLI`](https://github.com/protoLabsAI/protoCLI) — an AI agent that lives in your terminal.
- [`protoPatch`](https://github.com/protoLabsAI/protoPatch) — reviews code, patches the bugs it finds, and lands the PR.
- [`protoBanana`](https://github.com/protoLabsAI/protoBanana) — chat-native image generation and editing, served as an OpenAI-compatible provider on top of ComfyUI.
- [`protoWorkstacean`](https://github.com/protoLabsAI/protoWorkstacean) — a pluggable pubsub bus for agentic action.

## The engine

[`protoMaker`](https://github.com/protoLabsAI/protoMaker) is the dark factory: the orchestrator that ships most of what's here. Named agents pick features off a board, work in isolated git worktrees so they don't collide, and merge through the same CI any human PR goes through. A separate agent reviews the plan before code gets written, and the system escalates to a stronger model when a feature fails twice. 159 MCP tools wire it into the rest of the stack.

## What runs it

The substrate the experiments sit on. Most of it stays private; the parts worth sharing surface as the repos above.

- **protoLab** — LLM eval, training, and inference on 2× RTX PRO 6000 Blackwell (192 GB). LiteLLM gateway, Langfuse, vLLM.
- **mythxengine-sdk** — deterministic multi-agent worlds in Rust. Genre-agnostic; games plug in as packs.
- **homelab-iac** — the self-hosted Proxmox cluster it all runs on, behind Caddy, Cloudflare, and Tailscale.

## What we build with it

- **PilotProtocol** — mech-vs-mech agents fighting on a hex grid, with a click-through replay viewer that shows each model's reasoning a move at a time.
- **MythXEngine** — a TTRPG world-and-story generator built on mythxengine-sdk.
- [`protoVoice`](https://github.com/protoLabsAI/protoVoice) — a full-duplex voice agent you can interrupt mid-sentence. Live at [voice.proto-labs.ai](https://voice.proto-labs.ai).

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

Two people and a fleet of agents. We keep the numbers visible because a claim without one is just marketing.

## Where to find us

- [**protolabs.studio**](https://protolabs.studio) — home and blog
- [**hello@protolabs.consulting**](mailto:hello@protolabs.consulting) — consulting: pattern transfer, not retainer work
- [**@protoLabsAI**](https://x.com/protoLabsAI) — X
- [**Substack**](https://substack.com/@protolabsai) — long-form

---

**MIT licensed. No subscriptions, no microtransactions, no gated tiers** — pay-what-you-want and donations only. The infrastructure ships as patterns to study and steal. Bring your own hacking.
