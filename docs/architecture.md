# Architecture direction

This document describes a starting direction, not a completed design or a commitment to particular libraries.

## Shape of the system

- **Daemon:** owns agent lifecycle, sessions, scheduling and controlled background work. It should remain lightweight at idle and load expensive capabilities only when needed.
- **Agent harness:** assembles instructions and relevant context, invokes models and tools, tracks work and handles errors. Capability differences between models must be surfaced and evaluated.
- **Agent workspace:** holds each agent's identity, instructions, skills and memory. Agents are isolated by default; shared context and cross-agent access need explicit design and authorization.
- **Model connections:** an interface around providers, initially focused on the OpenAI paths supported by Hermes. Credentials belong in appropriate secure storage, never in project context files or Git.
- **Memory and learning:** investigate Hermes for storage, retrieval and learning mechanisms; preserve provenance and allow the owner to inspect, correct and remove remembered information. Separate memories from instructions and untrusted external content.
- **Clients:** a scrollback TUI and a QML GUI communicate with the same daemon. The GUI presents an agent sidebar, agent creation and a conversation view.

The process model, programming language, storage engine, transport and QML integration are undecided. Choose them after examining Hermes dependencies and measuring a working vertical slice.

## Context model

Inspired by OpenClaw, each agent can have readable files such as `SOUL.md` (identity, tone and values), `AGENTS.md` (role and operating instructions), and `USER.md` (owner context). Memory and skills are distinct from these files. These names are a proposed convention, not a finalized schema. Define precedence, context assembly, sharing and conflict resolution before implementation. External documents, retrieved memories and tool output are data, not automatic authority to change instructions.

## Autonomy and trust

The owner should be able to understand what an agent is doing, stop it, and set permissions. External side effects, sensitive access, continuous microphone use and changes to the agent's own behavior need explicit, appropriate owner controls. Background work must be bounded by resource budgets and observable; improvement should be evaluated and reversible before it is adopted. Actual permission policies and audio retention remain design decisions.

## Validation direction

Start with one end-to-end path: create an agent, converse, persist a useful memory, restart and retrieve it in a later conversation. Extend it to a second agent to check isolation, and exercise both clients against the same daemon. Measure idle and active resource usage and retrieval latency rather than assuming that extraction alone makes the application lightweight or fast.
