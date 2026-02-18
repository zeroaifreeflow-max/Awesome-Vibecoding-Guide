# Awesome Vibecoding Guide — AI Rules

## Project Awareness & Context

- **Always read `PLANNING.md`** at the start of a new conversation to understand the project's architecture, content structure, and conventions.
- **Check `TASK.md`** before starting a new task. If the task isn't listed, add it with a brief description and today's date.
- **Use the routing index** — Read `docs/_index/map.md` first to identify which domain a query falls into. Never guess which files to read.
- **Retrieve selectively** — Load only files listed for the matched domain. Target 2-4 files per query, never load all files at once.
  - Pricing queries → `docs/_index/pricing-quick-ref.md` first
  - Scaling queries → `docs/_index/scaling-quick-ref.md` first
  - Revenue streams → `docs/_index/streams.md` first

## Content Structure & Organization

- **Never create a file longer than 500 lines.** If a file approaches this limit, split into focused sub-files with a parent README as index.
- **Follow the numbered section pattern:** `00-introduction/` through `07-tech-stack/` for ordered content. Descriptive kebab-case for unordered sections (`business-operations/`, `project-funding/`).
- **Every directory needs a README.md** — overview paragraph, contents list with links, "Next/Back" navigation CTAs.
- **Use YAML frontmatter** on all content files. Schema: `doc_type`, `domain`, `streams`, `keywords`, `related_docs`, `token_estimate`.
- **Large files (>800 lines)** must be registered in `docs/_index/map.md` under "Large Files Reference" with selective reading hints.

## Content Quality & Consistency

- **Heading hierarchy:** H1 title → blockquote tagline → H2 sections → H3 subsections. Never skip levels.
- **Cross-references:** Use relative paths (`./file.md`, `../section/file.md`). End guides with `**Next:** [Link]` and `**Back to:** [Link]`.
- **Tables for comparisons** — pricing tiers, features, phases, tools. See `docs/01-money-map/README.md` for reference.
- **Frontmatter `related_docs`** must list 2-5 related files for cross-navigation.
- **No orphan files** — every .md must be linked from at least one README or index.

## Task Completion

- **Mark completed tasks in `TASK.md`** immediately after finishing them.
- Add new sub-tasks discovered during work to `TASK.md` under "Discovered During Work".

## Style & Conventions

- **File naming:** kebab-case (`pricing-economics.md`, `client-management.md`)
- **Directory naming:** kebab-case, optional number prefix (`01-money-map/`, `business-operations/`)
- **Content language:** English for docs. Thai for user-facing communication.
- **Emoji:** Strategic use only in root `README.md`. Avoid in `docs/` content.
- **Code blocks:** For formulas, CLI, ASCII diagrams, templates. Always specify language tag.
- **Service offers:** All use Bronze/Silver/Gold 3-tier framework (see `docs/01-money-map/packaging-models.md`).

## Existing Patterns to Follow

- **Section README:** `docs/01-money-map/README.md` — hook, overview, comparison table, contents, navigation
- **Playbook guide:** `docs/02-websites-playbook/pricing-economics.md` — frontmatter, title, tagline, structured sections
- **Agent command:** `.claude/commands/pricing-advisor.md` — Knowledge Base steps → How to Respond → Output Format → closing prompt
- **Routing domain:** `docs/_index/map.md` — trigger keywords, quick-ref links, primary files, stream variants
- **Quick reference:** `docs/_index/pricing-quick-ref.md` — dense data tables with source links, <300 tokens

## Agent Commands

| Command            | Purpose                                                  |
| ------------------ | -------------------------------------------------------- |
| `/pricing-advisor` | Calculate optimal pricing for any client scenario        |
| `/client-finder`   | Generate client acquisition strategies and outreach      |
| `/offer-designer`  | Design service packages and bundles                      |
| `/revenue-planner` | Project revenue, set targets, plan income streams        |
| `/scaling-advisor` | Plan business growth and team building                   |
| `/case-study`      | Document completed projects as case studies              |

## AI Behavior Rules

1. **Value-based thinking** — Never suggest hourly pricing. Always frame in terms of client value.
2. **Practical over theoretical** — Give specific numbers, scripts, and templates, not vague advice.
3. **Thai context aware** — When user discusses Thai market, adjust pricing and strategies accordingly.
4. **Honesty first** — Transparency builds trust, trust generates referrals.
5. **Progressive path** — Websites → Automations → Micro-SaaS. Each builds on the previous.
6. **Distinguish income types** — `01-money-map/` = client income. `project-funding/` = project/community funding.
7. **Never assume missing context** — Ask questions if uncertain. Never hallucinate file paths or data.
8. **Follow existing patterns** — When adding content, match the closest existing file's style and structure.
9. **Use frontmatter routing** — Check `doc_type` and `domain` fields to confirm relevance before reading full content.
10. **Don't refactor unprompted** — Document what IS, not what should be. Only restructure when explicitly asked.
