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

Claude Code CLI works with cost-effective providers by overriding the Anthropic API endpoint at the system level.

**Primary Setup (GLM Coding Plan):**

GLM provides an OpenAI-compatible API that works with Claude Code CLI. See the official setup guide:
- **[GLM + Claude Code Integration Guide](https://docs.z.ai/devpack/tool/claude)**

**Secondary Setup (Synthetic.new):**

Synthetic.new also provides Claude Code compatibility. See:
- **[Synthetic + Claude Code Integration Guide](https://dev.synthetic.new/docs/guides/claude-code)**

**How it works:**
Both providers require overriding the `ANTHROPIC_BASE_URL` and `ANTHROPIC_API_KEY` environment variables at the system level. The documentation above walks through the exact setup steps.

**Note:** You'll need to reconfigure environment variables when switching between providers (GLM ↔ Synthetic).

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

Provider switching requires updating environment variables. A simple approach:

```bash
# In your .zshrc or .bashrc, create functions to switch providers:

# Switch to GLM (primary daily driver)
glm-mode() {
  export ANTHROPIC_BASE_URL="https://api.z.ai/v1"  # Check GLM docs for exact URL
  export ANTHROPIC_API_KEY="your-glm-api-key"
  echo "Switched to GLM"
}

# Switch to Synthetic (for MiniMax/Kimi)
synthetic-mode() {
  export ANTHROPIC_BASE_URL="https://api.synthetic.new/v1"  # Check Synthetic docs
  export ANTHROPIC_API_KEY="your-synthetic-api-key"
  echo "Switched to Synthetic"
}
```

**Important:** Check the official integration guides for exact URLs and configuration:
- [GLM + Claude Code](https://docs.z.ai/devpack/tool/claude)
- [Synthetic + Claude Code](https://dev.synthetic.new/docs/guides/claude-code)

## Recent Improvements Worth Noting

- **Opus 4.5 & Haiku 4.5 support** — Latest models with automatic fallbacks
- **Sandbox mode** — Experimental BashTool sandboxing for safer execution
- **Improved permission prompts** — Clearer UX for tool approvals
- **Session resume** — Pick up where you left off seamlessly
- **Branch filtering** — Better navigation in git-heavy workflows

## Installation & Setup

```bash
# Install via npm
npm install -g @anthropic-ai/claude-code

# Verify installation
claude --version
```

**Provider Configuration:**

To use with GLM or Synthetic instead of native Anthropic, configure environment variables as documented in:
- [GLM + Claude Code](https://docs.z.ai/devpack/tool/claude)
- [Synthetic + Claude Code](https://dev.synthetic.new/docs/guides/claude-code)

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
