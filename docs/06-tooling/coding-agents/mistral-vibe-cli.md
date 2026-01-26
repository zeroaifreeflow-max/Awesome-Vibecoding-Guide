# Mistral Vibe CLI — Agentic Coding in Your Terminal

> **Terminal-Powered Intelligence**: Mistral Vibe CLI brings Devstral 2's capabilities directly to your command line with agentic workflows and deep project integration.

## Core Capabilities

### Agentic Workflows
- **Multi-Step Reasoning**: Breaks complex tasks into manageable steps
- **Tool Integration**: Seamless use of grep, shell commands, and file operations
- **Stateful Sessions**: Maintains context across interactions

### Project Intelligence
- **File Structure Awareness**: Understands your entire codebase
- **Git Status Integration**: Knows what's changed and staged
- **Cross-File Reasoning**: Handles dependencies and imports intelligently

### Safety Features
- **Tool Approval**: Default confirmation for potentially destructive operations
- **Transparent Operations**: Clear logging of all actions
- **Configurable Permissions**: Fine-grained control via config.toml

## Practical Usage Patterns

### 1. Complex Refactoring
```bash
vibe "Convert the monolithic auth service to microservices architecture"
# Agent will:
# 1. Analyze current structure
# 2. Propose migration plan
# 3. Implement step-by-step with your approval
```

### 2. Bug Hunting
```bash
vibe "The memory leak in @src/api/ occurs during high load - diagnose and fix"
# Agent will:
# 1. Identify potential causes
# 2. Suggest diagnostic approaches
# 3. Implement targeted fixes
```

### 3. Documentation Generation
```bash
vibe "Create comprehensive API documentation for @src/endpoints/ with examples"
# Agent will:
# 1. Analyze all endpoint files
# 2. Generate Markdown documentation
# 3. Include usage examples
```

## Configuration Guide

### Basic Setup
```toml
# ~/.vibe/config.toml
[default]
model = "devstral-2"
auto_approve = false
verbose = true
```

### Advanced Options
```toml
[models.devstral-2]
temperature = 0.3
max_tokens = 4096

[tools]
enable_grep = true
enable_shell = true
safe_mode = true
```

## Performance Tips

### Context Management
- **Focus Areas**: Use `@file` or `@directory` references
- **Session Scope**: Start with broad context, narrow as needed
- **Memory**: Clear sessions between unrelated tasks

### Token Efficiency
- **Model Selection**: Use Devstral Small 2 for simpler tasks
- **Prompt Structure**: Be specific about scope and requirements
- **Iterative Approach**: Break large tasks into smaller steps

## Troubleshooting

### Common Issues
- **Context Limits**: "Project too large" warnings
  - Solution: Specify subdirectories or files
- **Permission Denied**: Tool execution blocks
  - Solution: Check config.toml permissions
- **Model Timeouts**: Long-running operations
  - Solution: Break into smaller tasks

### Debugging
```bash
vibe --verbose --debug "Your command here"
# Shows detailed execution logs
```

## When to Choose Mistral Vibe CLI

### Ideal Scenarios
✅ **Complex Architecture Work** — Multi-file refactoring
✅ **Open Source Projects** — Transparent, controllable tooling
✅ **Budget-Conscious Development** — Free tier with professional results
✅ **Terminal-Centric Workflows** — Prefer CLI over IDE integrations

### Consider Alternatives When
❌ **Simple Edits** — Overkill for single-file changes
❌ **GUI Preferences** — If you prefer visual interfaces
❌ **Enterprise Constraints** — When specific compliance requirements exist

## The Developer Experience

Mistral Vibe CLI transforms your terminal into an intelligent coding environment. With Devstral 2's reasoning capabilities and the agent's project awareness, you get professional-grade assistance without leaving your preferred workflow. The generous free tier and open-source foundation make it an excellent choice for vibecoders who want both power and transparency.