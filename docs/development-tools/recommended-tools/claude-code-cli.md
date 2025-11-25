# Claude Code CLI — Primary Coding Agent 🚀

> **The Main Driver**: Claude Code CLI has become my primary coding agent thanks to recent improvements in plan mode, multi-agent architecture, and global plan persistence.

## Why Claude Code CLI is Now #1

Claude Code's recent releases (v2.0.28+) introduced features that fundamentally changed how I approach AI-assisted development. The combination of improved planning, multi-agent coordination, and efficient codebase exploration makes it superior for most everyday coding tasks.

### Key Differentiators

**Plan Mode Superpowers:**
- Plans are now saved globally and referenced across sessions
- Dedicated Plan subagent builds more precise, actionable plans
- Plans persist as markdown files for review, sharing, and iteration
- Execute approved plans with confidence knowing the context is preserved

**Multi-Agent Architecture:**
- Launch specialized subagents for different tasks (explore, plan, implement)
- Subagents can be resumed, maintaining context across interactions
- Dynamic model selection — use the right model for each subtask
- Parallel agent execution for maximum efficiency

**Explore Subagent:**
- Haiku-powered efficient codebase searching
- Reduces context overhead by intelligently navigating large codebases
- Find relevant files and patterns without loading everything into context
- Perfect for understanding unfamiliar codebases quickly

**Plugin & Extensibility:**
- Plugin system (v2.0.12+) for custom commands, agents, and hooks
- MCP server marketplace integration
- Team-shareable configurations and workflows
- Extend functionality without leaving the CLI

## Integration with Providers

Claude Code CLI works seamlessly with cost-effective providers:

**Primary Setup (GLM Coding Plan):**
```bash
# Configure for GLM-4.6 — reliable daily driver
claude config set provider glm
claude config set model glm-4.6
```

**Secondary Setup (Synthetic.new):**
```bash
# Switch to Synthetic when you need MiniMax or Kimi
claude config set provider synthetic
claude config set model minimax-m2  # or kimi-thinking
```

The BYOK (Bring Your Own Key) support means you're not locked into expensive subscriptions — use your preferred provider at their rates.

## When to Use Claude Code vs Droid

| Scenario | Use Claude Code | Use Droid |
|----------|-----------------|-----------|
| Quick iterations & tight loops | ✅ Best choice | Overkill |
| Single-file changes & refactors | ✅ Best choice | Overkill |
| Multi-file features | ✅ Best choice | Good option |
| Exploring new codebases | ✅ Explore subagent | Manual |
| Large projects with formal specs | Consider | ✅ Best choice |
| Team coordination with phases | Consider | ✅ Best choice |
| Spec-driven enterprise work | Consider | ✅ Best choice |

**Rule of thumb:** Start with Claude Code for most work. Switch to Droid when you need formal specification phases or structured team workflows.

## Pro Tips for Maximum Productivity

### 1. Use Plan Mode for Complex Tasks
```bash
# Before implementing, let Claude plan it out
claude --plan "Add user authentication with OAuth2"
# Review the plan, approve, then execute
```

### 2. Leverage the Explore Subagent
Don't manually grep through codebases. Let the Explore subagent find relevant files:
```bash
claude "Where is the authentication middleware implemented?"
# Explore subagent efficiently searches without loading entire codebase
```

### 3. Save and Reference Plans
Plans persist globally — reference them in future sessions:
```bash
claude "Continue implementing the auth plan from yesterday"
# Claude references the saved plan automatically
```

### 4. Parallel Agent Execution
For independent tasks, launch multiple agents:
```bash
claude "Run tests AND check for linting issues"
# Independent tasks run in parallel for faster feedback
```

### 5. Configure for Your Workflow
Set up provider switching for different needs:
```bash
# GLM for routine work (cost-effective)
alias cc-glm="claude --provider glm"

# Synthetic for when you need Kimi thinking
alias cc-kimi="claude --provider synthetic --model kimi-thinking"
```

## Recent Improvements Worth Noting

- **Opus 4.5 & Haiku 4.5 support** — Latest models with automatic fallbacks
- **Sandbox mode** — Experimental BashTool sandboxing for safer execution
- **Improved permission prompts** — Clearer UX for tool approvals
- **Session resume** — Pick up where you left off seamlessly
- **Branch filtering** — Better navigation in git-heavy workflows

## Installation & Setup

```bash
# Install via npm
npm install -g @anthropic/claude-code

# Or via homebrew
brew install claude-code

# Configure your provider
claude config set provider glm
claude config set api-key YOUR_API_KEY
```

## The Bottom Line

Claude Code CLI is now my primary coding agent because it strikes the perfect balance:
- **Fast** for quick iterations and small changes
- **Powerful** with multi-agent architecture for complex work
- **Efficient** with Explore subagent for codebase navigation
- **Flexible** with BYOK provider support (GLM, Synthetic, etc.)
- **Persistent** with global plan storage across sessions

For most vibecoding workflows, Claude Code CLI gets the job done faster and more efficiently than alternatives. Reserve [Droid CLI](./droid-cli.md) for when you genuinely need formal specification phases and structured team coordination.

---

**Related:**
- [Droid CLI](./droid-cli.md) — For spec-driven development
- [GLM Coding Plan](../../ai-model-providers/glm-coding-plan.md) — Primary provider
- [Synthetic.new](../../ai-model-providers/synthetic-new.md) — For model flexibility

Back: [Development Tools](../README.md)
