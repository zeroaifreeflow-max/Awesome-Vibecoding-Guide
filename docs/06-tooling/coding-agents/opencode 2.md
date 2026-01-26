# OpenCode + oh-my-opencode

> Terminal-native BYOK coding agent — connect any provider, work at terminal speed.

## Overview

[OpenCode](https://github.com/opencode-ai/opencode) is a fast, terminal-based AI coding agent that works with any OpenAI-compatible API. It's the vibecoder's choice when you want full control over your model provider and prefer keyboard-driven workflows.

**Why OpenCode matters for making money:**
- **Zero vendor lock-in** — Use whatever provider gives you the best price/performance today
- **Terminal speed** — No GUI overhead means faster iteration cycles
- **Cost control** — Connect to budget providers during heavy coding sessions

## Installation

```bash
# macOS (Homebrew)
brew install opencode-ai/tap/opencode

# Linux/macOS (Go install)
go install github.com/opencode-ai/opencode@latest

# Or download binary from releases
curl -fsSL https://github.com/opencode-ai/opencode/releases/latest/download/opencode_$(uname -s)_$(uname -m).tar.gz | tar xz
sudo mv opencode /usr/local/bin/
```

Verify installation:
```bash
opencode --version
```

## oh-my-opencode — Essential Extensions

[oh-my-opencode](https://github.com/phthhieu/oh-my-opencode) adds quality-of-life improvements:

```bash
# Install oh-my-opencode
git clone https://github.com/phthhieu/oh-my-opencode.git ~/.oh-my-opencode
echo 'source ~/.oh-my-opencode/opencode.sh' >> ~/.zshrc  # or ~/.bashrc
```

**What it adds:**
- **Keybindings** — `Ctrl+O` to launch, `Ctrl+K` for quick commands
- **Session management** — Resume previous conversations
- **Git integration** — Auto-context from current repo
- **Output formatting** — Better display of code blocks and diffs

## Provider Configuration

OpenCode connects to any OpenAI-compatible API. Create `~/.opencode/config.yaml`:

### Synthetic.new (Free Claude/GPT Access)

```yaml
providers:
  synthetic:
    base_url: "https://api.synthetic.new/v1"
    api_key: "your-synthetic-api-key"
    models:
      - claude-sonnet-4-20250514
      - gpt-4o

default_provider: synthetic
default_model: claude-sonnet-4-20250514
```

### MiniMax (Budget Option)

```yaml
providers:
  minimax:
    base_url: "https://api.minimax.chat/v1"
    api_key: "your-minimax-api-key"
    models:
      - abab6.5s-chat

default_provider: minimax
default_model: abab6.5s-chat
```

### GLM (Chinese Market / Cost Effective)

```yaml
providers:
  glm:
    base_url: "https://open.bigmodel.cn/api/paas/v4"
    api_key: "your-glm-api-key"
    models:
      - glm-4-plus
      - glm-4-flash

default_provider: glm
default_model: glm-4-plus
```

### Multi-Provider Setup (Recommended)

```yaml
providers:
  synthetic:
    base_url: "https://api.synthetic.new/v1"
    api_key: "${SYNTHETIC_API_KEY}"
    models: [claude-sonnet-4-20250514]
  minimax:
    base_url: "https://api.minimax.chat/v1"
    api_key: "${MINIMAX_API_KEY}"
    models: [abab6.5s-chat]

# Switch with: opencode --provider minimax
default_provider: synthetic
```

## When to Use OpenCode

| Scenario | OpenCode | Why |
|----------|----------|-----|
| Quick terminal tasks | ✅ Best choice | Fastest startup, no context switching |
| BYOK with budget providers | ✅ Best choice | Connect any OpenAI-compatible API |
| Heavy iteration sessions | ✅ Good | Switch to cheap providers mid-session |
| Complex multi-file refactors | ⚠️ Consider alternatives | Claude Code CLI has better file handling |
| Need visual diffs | ❌ Use ZED or Cursor | Terminal diffs are limited |

## Workflow Integration

**Daily Pattern:**
1. **Morning setup** — `opencode` in project directory, uses git context
2. **Quick fixes** — Stay in OpenCode for speed
3. **Heavy sessions** — Switch provider: `opencode --provider minimax`
4. **Complex work** — Move to Claude Code CLI when needed

**Keyboard workflow:**
```bash
# Launch in current directory
opencode

# Launch with specific provider
opencode --provider synthetic

# Launch with specific model
opencode --model glm-4-flash

# Resume last session
opencode --resume
```

## Efficiency Tips

1. **Set up aliases** for your common configurations:
   ```bash
   alias oc="opencode"
   alias oc-cheap="opencode --provider minimax"
   alias oc-quality="opencode --provider synthetic --model claude-sonnet-4-20250514"
   ```

2. **Use environment variables** for quick switching:
   ```bash
   export OPENCODE_PROVIDER=synthetic  # Default for session
   ```

3. **Combine with tmux** — Keep OpenCode running in a dedicated pane

4. **Git hooks** — Auto-context from staged files:
   ```bash
   # In .git/hooks/pre-commit
   opencode --context "$(git diff --cached)" --prompt "Review these changes"
   ```

## Limitations and Workarounds

| Limitation | Workaround |
|------------|------------|
| No visual file tree | Use `tree` command, pipe to context |
| Limited multi-file edits | Break into smaller tasks or use Claude Code CLI |
| No built-in git UI | Combine with `lazygit` in split terminal |
| Provider rate limits | Configure multiple providers, switch when throttled |

## Resources

- [OpenCode Repository](https://github.com/opencode-ai/opencode)
- [oh-my-opencode Extensions](https://github.com/phthhieu/oh-my-opencode)
- [Synthetic.new API](https://synthetic.new) — Free tier for OpenAI-compatible access
