# Mistral Vibe — Devstral 2 Powered Coding

> **The Open Source Powerhouse**: Mistral Vibe brings the cutting-edge Devstral 2 model to your terminal with a generous free tier and professional-grade capabilities.

## Why Mistral Vibe Stands Out

### Devstral 2 Excellence
- **State-of-the-Art Performance**: 72.2% on SWE-bench Verified
- **Cost Efficiency**: 7x more efficient than alternatives
- **Model Options**: Devstral 2 (123B) and Devstral Small 2 (24B)

### Generous Free Tier
- **Current Offering**: Free access to Devstral 2 models via API
- **Quota**: Generous limits for real-world projects
- **Future Pricing**: Transparent roadmap ($0.40-$2.00 per million tokens)

### Project-Aware Intelligence
- **Deep Context**: Understands entire codebase structure
- **Git Integration**: Aware of repository state and changes
- **Architecture Reasoning**: Handles complex refactoring scenarios

## Getting Started

### Installation Options
```bash
# One-line install
curl -LsSf https://mistral.ai/vibe/install.sh | bash

# Using uv
uv tool install mistral-vibe

# Using pip
pip install mistral-vibe
```

### First Run
```bash
vibe --help  # Explore available commands
vibe         # Enter interactive mode
```

## Practical Workflows

### 1. Interactive Development
```bash
vibe
> @src/main.py needs error handling improvement
```

### 2. Project-Level Refactoring
```bash
vibe --auto-approve "Modernize the authentication system across all services"
```

### 3. Smart Code Navigation
```bash
vibe "Find all TODO comments and suggest implementations"
```

## Best Practices

### Configuration Tips
- **Auto-Approval**: Use `--auto-approve` for trusted workflows
- **Context Management**: Reference files with `@` prefix
- **Safety**: Default tool approval ensures control

### Performance Optimization
- **Model Selection**: Choose Devstral Small 2 for lighter tasks
- **Context Pruning**: Focus on relevant project areas
- **Session Management**: Use persistent sessions for large projects

## Integration Points

### With Existing Toolchain
- **Primary Use**: Complex refactoring and architecture work
- **Backup Role**: When other providers hit limits
- **Specialty**: Open-source project compatibility

### Zed IDE Integration
- Official extension available
- Seamless terminal-to-IDE workflow
- Enhanced project awareness

## The Bottom Line

Mistral Vibe CLI delivers professional-grade coding assistance powered by Devstral 2, with a generous free tier that makes it accessible for projects of all sizes. Its project-aware intelligence and open-source foundation make it a standout choice for vibecoders who value both performance and transparency.