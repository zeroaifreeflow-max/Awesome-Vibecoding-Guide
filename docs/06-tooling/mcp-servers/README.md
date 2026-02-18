# MCP Servers

> Model Context Protocol servers for enhanced AI capabilities.

## What Are MCP Servers?

MCP (Model Context Protocol) servers extend your AI agents with additional capabilities:
- Access external data sources
- Integrate with tools and services
- Enhance reasoning and context

## Recommended MCP Servers

| Server | Purpose |
|--------|---------|
| **[Context7](#context7--documentation-management)** | Documentation access and retrieval |
| **[DevTools](#devtools--testing--debugging)** | Browser automation and testing |
| **[Sequential Thinking](sequential-thinking-mcp.md)** | Structured cognitive enhancement |
| **[Task Manager](task-manager-mcp.md)** | Persistent task tracking |
| **[Shadcn](shadcn-mcp.md)** | UI component access |

## Setup

MCP servers integrate with Claude Code CLI and other compatible agents:

```bash
# Add to your Claude Code configuration
# See individual server pages for specific setup
```

## Why Use MCP?

| Capability | Benefit |
|------------|---------|
| **Context7** | Access up-to-date docs without copy-paste |
| **DevTools** | Test in browser automatically |
| **Sequential Thinking** | Better problem decomposition |
| **Task Manager** | Track work across sessions |
| **Shadcn** | Quick access to UI patterns |

## Minimal Setup

Start with these essentials:
1. **Context7** — Documentation is always needed
2. **Task Manager** — Track complex projects
3. **Sequential Thinking** — Better AI reasoning

Add others as your workflow demands.

---

## Context7 — Documentation Management

- Knowledge about what exactly should be done regarding chosen tech stack
- Documentation on given framework
- Critical for long-term projects
- Super critical for debugging issues — asking to use Context7 MCP to find documentation on a given issue usually helps the LLM resolve the problem

## DevTools — Testing & Debugging

### Testing breakthrough

- 95% less context usage than Playwright
- Intelligent navigation for web development tests
- Automatic debugging: console logs, navigation, 500 errors

### Workflow

- Launch the MCP
- Inform the agent about issues
- The agent autonomously gathers data, debugs, and resolves

Pro tip: It's more efficient to tell the LLM "use MCP" instead of writing a long debugging prompt.

Pro tip 2: For web development, it can even perform its own tests using Chrome DevTools MCP when prompted correctly.
