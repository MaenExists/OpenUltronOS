# OpenUltronOS

## Why this exists

OpenUltronOS is the personal intelligence infrastructure of its creator. Its defining inspiration is the relationship between Tony Stark and JARVIS: a deeply capable intelligence woven into the inventor's life and work, able to understand an intent, reason alongside him, operate systems, surface what matters and help turn ambitious ideas into reality. It is a partner in the workshop and in the wider world, present across both consequential work and everyday life.

The ambition is an external intelligence that can exceed its owner in particular tasks, bring knowledge and perspective he does not have, and do substantial work on his behalf. It should extend his reach and sharpen his thinking, giving him more attention for the decisions, ideas and problems that matter most. It should challenge weak assumptions and bring better answers, not merely agree or wait for detailed instructions.

**INVENT. BUILD. TRANSFORM. DESTROY.** Invent new possibilities; build working things; transform existing systems and ways of working; destroy obstacles, obsolete assumptions and work that no longer serves the mission. This is a creative and operational ambition, grounded in the owner's actual intent and authority.

This is a personal system first, built around its owner's goals and way of working. It is an infrastructure for multiple distinct assistants, not a single monolithic persona. Every agent, whatever its specialty or personality, should embody the same JARVIS-like instinct: understand the owner and the mission, think independently, take useful initiative and follow through. See [the shared agent ethos](docs/agent-ethos.md).

## What we are building

A lightweight, persistent agent runtime with a carefully engineered harness around interchangeable models. The harness should give agents useful context, memory, tools, learning and reliable execution; intelligence should not depend on a single model vendor. Models differ in capabilities, so equal results across every model are an aspiration to test, not a guarantee.

The long-term ambition is a system that can listen, think proactively and improve while idle. Continuous listening, background thinking and self-improvement require explicit controls, resource limits, privacy and observable behavior. They are ambitions, not claims about an existing implementation. The owner stays in control of consequential actions and system changes.

## First version

Build a small but real foundation that can grow:

- A lightweight daemon that hosts multiple individually configured agents and their conversations.
- Per-agent identity, context, memory and skills, with separation by default and deliberate sharing when needed.
- OpenAI connections, including the OpenAI authentication and connection paths available in Hermes, subject to an implementation and compatibility audit.
- Persistent memory and learning mechanisms adapted from Hermes Agent after identifying the necessary components and dependencies.
- A simple scrollback terminal interface inspired by Codex CLI.
- A QML desktop interface inspired by the modern Grok Bots app: a sidebar lists agents, supports creating one and opens its conversation. Inspiration is for interaction and feel, not a requirement to copy proprietary assets.
- Clear controls for agent activity, external actions and access to personal information.

The first version should establish a useful conversation and memory loop that can support a substantive research or building task, not just daily organization. Always-on audio and autonomous idle improvement may be staged after that foundation; their exact initial scope remains to be decided. More integrations and features can follow as the system proves useful.

## Engineering direction

Study and selectively extract the relevant parts of [Hermes Agent](https://github.com/NousResearch/hermes-agent): OpenAI connections, persistent memory, retrieval and learning. The intended approach is to fork and strip Hermes down to the necessary atoms, then build the rest of OpenUltronOS independently. Map dependencies, licenses, attribution and update strategy before copying or modifying code. Do not assume the extracted pieces are independently portable or that their performance will carry over unchanged.

Use [OpenClaw's agent workspace](https://docs.openclaw.ai/agent-workspace) as inspiration for human-readable context files such as `SOUL.md`, with a distinct workspace per agent. Adapt the ideas to this project rather than adopting the whole system. See [architecture](docs/architecture.md) and [research](docs/research.md) for boundaries and open questions.

## What success looks like

The owner can create an agent, give it a clear purpose, talk with it in the desktop or terminal interface, return later and see it use relevant memory. The agent helps advance a meaningful idea or project through research, critical thinking and useful execution, while also handling everyday work. It remains understandable and responsive, and earns trust through visible actions and owner control. Measure idle resource use, memory retrieval quality, task completion and model portability on real hardware and workflows as the system develops; targets are not yet set.
