# Project Planning — Awesome Vibecoding Guide

## Overview
A comprehensive business knowledge base for **vibecoding freelancers** — people who use AI-assisted coding to build websites, automations, and micro-SaaS products for real clients. The knowledge base lives in `./docs/` (177 markdown files, ~64,000 total lines). Designed for both human reading and AI agent consumption via a RAG-optimized routing layer.

## Tech Stack (Detected)

| Layer | Technology | Config File |
|-------|-----------|-------------|
| Content Format | Markdown (.md) | — |
| Metadata | YAML Frontmatter | In-file `---` blocks |
| Version Control | Git | `.git/` |
| AI Integration | Claude Code | `.claude/commands/`, `.claude/agents/` |
| Routing Layer | Custom `_index/` system | `docs/_index/map.md` |
| License | MIT | `LICENSE` |

## Architecture

### Content Organization
```
docs/
├── _index/                    # RAG ROUTING LAYER (agents read first)
│   ├── map.md                 # Master query routing → 10 domains
│   ├── streams.md             # Revenue streams quick reference
│   ├── pricing-quick-ref.md   # Consolidated pricing data
│   └── scaling-quick-ref.md   # Scaling phases quick reference
├── 00-introduction/           # Philosophy, core principles
├── 01-money-map/              # CLIENT INCOME: pricing, packaging, offers
├── 02-websites-playbook/      # Stream 1: Local business websites ($300-1,000)
├── 03-automations-playbook/   # Stream 2: AI automations ($500-3,000 + retainer)
├── 04-micro-saas-playbook/    # Stream 3: Micro-SaaS ($50-500/month)
├── 05-delivery-system/        # Quality, prompting, workflow, troubleshooting
│   ├── context-management/    # Context optimization for AI
│   ├── prompting/             # AI prompting techniques
│   ├── quality-standards/     # Performance, security, testing, UX, SEO
│   ├── troubleshooting/       # Debugging & recovery
│   └── workflow/              # Dev phases, git, deployment
├── 06-tooling/                # AI tools, IDEs, MCP servers, providers
├── 07-tech-stack/             # Astro, Tailwind, Cloudflare ecosystem
├── business-operations/       # Time, client, financial, project management
├── project-funding/           # GitHub Sponsors, Patreon, affiliate, consulting
├── case-studies/              # Templates for documenting client work
├── legal/                     # Contracts, compliance, IP
├── appendix/                  # Cheat sheets, glossary, templates, cross-reference
└── _archive/                  # Deprecated content (31 files, not maintained)
```

### AI Agent System
```
.claude/
├── agents/
│   └── orchestrator.md        # Lead strategist — delegates to domain agents
└── commands/                  # 6 slash commands (user-invocable)
    ├── pricing-advisor.md     # Pricing calculation & value framing
    ├── client-finder.md       # Client acquisition strategies
    ├── offer-designer.md      # Bronze/Silver/Gold package design
    ├── revenue-planner.md     # Revenue projections & stream planning
    ├── scaling-advisor.md     # 5-phase growth planning
    └── case-study.md          # ROI-focused project documentation
```

### RAG Routing Flow
```
User Query → _index/map.md (match domain by trigger keywords)
           → Quick-ref file (pricing / scaling / streams)
           → 2-4 domain-specific files (selective loading)
           → Agent generates response
```

## Key Patterns Found

1. **Routing-first retrieval** — All agents read `_index/map.md` first. 10 domains with trigger keywords map to exact file paths.
2. **YAML frontmatter** — Schema: `doc_type` (index/guide/playbook/reference/deep-dive/template), `domain`, `streams[]`, `keywords[]`, `related_docs[]`, `token_estimate`.
3. **3-tier packaging** — Bronze/Silver/Gold applied to all services. Silver = target tier (best value anchor).
4. **Progressive revenue path** — Websites → Automations → Micro-SaaS, each building on client relationships.
5. **Section READMEs as indexes** — Every directory has README.md with overview + contents list + navigation CTAs.

## File Reference Guide

| When creating... | Follow the pattern in... |
|-----------------|------------------------|
| New docs section | `docs/01-money-map/README.md` |
| New playbook guide | `docs/02-websites-playbook/pricing-economics.md` |
| New agent command | `.claude/commands/pricing-advisor.md` |
| New routing domain | `docs/_index/map.md` |
| New quick-ref file | `docs/_index/pricing-quick-ref.md` |
| New case study template | `docs/case-studies/templates/website-project.md` |
| New cheat sheet | `docs/appendix/cheat-sheets/git-commands.md` |

## Core Business Model

### Three Revenue Streams
| Stream | Price Range | Recurring | Difficulty |
|--------|-----------|-----------|------------|
| Websites | $300-1,000/site | $25-100/mo maintenance | Beginner |
| Automations | $500-3,000 setup | $50-300/mo retainer | Intermediate |
| Micro-SaaS | $500-2,000 setup | $50-500/mo subscription | Advanced |

### Pricing Formula
```
Client Value = (Time Saved × Hourly Rate) + Revenue Increase + Cost Reduction
Your Price   = 10-20% of Client Value
```

### 5 Scaling Phases
| Phase | Revenue/mo | Structure |
|-------|-----------|-----------|
| 1. Solo | $3-5k | You do everything |
| 2. Leveraged | $8-12k | + first contractor |
| 3. Team | $20-25k | + PM + 2-3 contractors |
| 4. Agency | $50-80k | 15-20 people |
| 5. Product | $100-500k | SaaS + productized |

## Known Technical Debt
- **Inconsistent frontmatter** — ~22 of ~80+ content files have YAML metadata; rest need adding
- **6 monolith files** — Files >1,000 lines in `05-delivery-system/` (listed in `_index/map.md`); candidates for splitting
- **Orphan file** — `myBiz - Ai Automation.md` at root (1-line stub, not linked anywhere)
- **Playbook READMEs lack frontmatter** — `02-`, `03-`, `04-` README.md files missing YAML metadata
- **No .editorconfig** — No formatting config for consistent whitespace/line endings
