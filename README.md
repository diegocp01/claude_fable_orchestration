# Use Fable 5 as orchestrator and Opus + Codex to execute (to save fable usage):

- **Fable 5 (max reasoning)** = orchestrator
- **Opus** = deep reasoning subagent
- **Sonnet** = mechanical work subagent
- **Codex** = peer Sr. engineer, different perspective

## Setup:

1. Set Fable 5 as your main model  In Claude Code: `/model` → Fable 5 → reasoning /effort to max

2. Create 2 subagents with `/agents` In Claude Code:

   **deep-reasoner** → pinned to opus "Use for reasoning-heavy phases, architecture, debugging complex issues, algorithm design. Think thoroughly, return a concise conclusion the orchestrator can act on."

   **fast-worker** → pinned to sonnet "Use for mechanical tasks, boilerplate, tests, formatting, simple edits. Execute efficiently."

3. Add OpenAI's official Codex plugin (install codex cli in your computer first), In Claude Code type:

```text
/plugin marketplace add openai/codex-plugin-cc
 /plugin install codex@openai-codex
 /codex:setup
```

4. Drop the contents of [CLAUDE.md](CLAUDE.md) in your folder.

5. Then prompt Fable like a tech lead:  "Goal: [what you want] Context: [files, constraints] You're the lead. Delegate reasoning to deep-reasoner, grunt work to fast-worker, fresh-perspective problems to Codex. Show me your plan first, then execute."

That's it.
