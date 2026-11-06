# Research and decisions

## Upstream starting points

- [Hermes Agent repository](https://github.com/NousResearch/hermes-agent) and [provider documentation](https://github.com/NousResearch/hermes-agent/blob/main/website/docs/integrations/providers.md): inventory all OpenAI connection and authentication paths, their dependencies and constraints. The docs describe an OpenAI Codex OAuth path; the complete set still needs a source-level audit.
- [OpenClaw agent workspace](https://docs.openclaw.ai/agent-workspace) and [multi-agent concepts](https://github.com/openclaw/openclaw/blob/main/docs/concepts/multi-agent.md): reference for per-agent workspace and context-file ideas.

Before extraction, pin the upstream revision studied, map memory and learning code and dependencies, identify applicable licenses and attribution obligations, and record what is retained or replaced. Test memory quality, speed and isolation in OpenUltronOS rather than assuming upstream behavior transfers. No upstream code has been imported yet.

## Open decisions

- Which Hermes memory and learning mechanisms are essential, and how can they be separated without pulling in unrelated features?
- Which OpenAI authentication and API paths work for the owner's accounts and comply with their applicable terms?
- What languages, storage, daemon protocol and QML bridge give the best practical balance of simplicity, performance and maintainability?
- What hardware and operating systems are the initial targets, and what idle RAM and latency budgets are acceptable?
- What memory can agents share, and how does the owner inspect, correct, delete or export it?
- What constitutes safe, useful idle learning, and how are proposed changes reviewed, tested and rolled back?
- When should always-listening audio be introduced, and what are the activation, indicator, storage and privacy controls?
- Which useful daily-life workflows and integrations should follow the initial conversation and memory slice?

These are questions for discovery, not blockers to documenting the vision. Record decisions and evidence as implementation begins.
