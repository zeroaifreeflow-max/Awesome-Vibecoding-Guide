---
doc_type: index
domain: routing
keywords: [index, map, routing, navigation, agent]
token_estimate: 350
---

# Documentation Routing Map

> Agents: Read this file FIRST to identify which docs to load for any query.
> Load only the files listed for the matched domain. Target 2-4 files per query.

## Domain: Pricing & Packaging

**Triggers:** price, cost, rate, package, tier, quote, charge, discount, bundle

**Quick ref:** [pricing-quick-ref.md](pricing-quick-ref.md) (start here for numbers)

**Primary files:**

- `docs/01-money-map/pricing-fundamentals.md` — Core philosophy (never hourly, value-based)
- `docs/01-money-map/pricing-strategies.md` — Advanced: anchoring, ROI-based, psychology
- `docs/01-money-map/packaging-models.md` — Bronze/Silver/Gold 3-tier framework
- `docs/01-money-map/offer-design.md` — Productized vs custom, scope management

**Stream-specific pricing:**

- Websites: `docs/02-websites-playbook/pricing-economics.md`
- Automations: `docs/03-automations-playbook/pricing-automations.md`
- Micro-SaaS: `docs/04-micro-saas-playbook/scoping-pricing.md`

## Domain: Client Acquisition & Sales

**Triggers:** client, find, prospect, outreach, lead, sales, pitch, script, marketing

**Primary files:**

- `docs/02-websites-playbook/client-acquisition.md` — Facebook, LinkedIn, Google Maps, walk-in
- `docs/02-websites-playbook/value-proposition.md` — How to position your offer
- `docs/01-money-map/offer-design.md` — Clear offer structure

**Stream-specific acquisition:**

- Automations: `docs/03-automations-playbook/finding-clients.md`
- Micro-SaaS: `docs/04-micro-saas-playbook/finding-clients.md`

## Domain: Client Management & Delivery

**Triggers:** client management, onboarding, handoff, communication, relationship, referral

**Primary files:**

- `docs/02-websites-playbook/client-management.md` — Honesty-first, referral strategy
- `docs/business-operations/client-management.md` — CRM, lifecycle, email templates
- `docs/02-websites-playbook/delivery-sop.md` — 48-hour website SOP
- `docs/03-automations-playbook/delivery-playbook.md` — Automation delivery process
- `docs/04-micro-saas-playbook/client-handoff.md` — SaaS handoff & training

## Domain: Revenue & Financial Planning

**Triggers:** revenue, income, money, profit, ROI, financial, forecast, budget

**Quick ref:** [streams.md](streams.md) (start here for revenue potential)

**Primary files:**

- `docs/01-money-map/README.md` — Three revenue streams overview
- `docs/01-money-map/choosing-your-path.md` — Which stream to start with
- `docs/02-websites-playbook/roi-tracking.md` — Tool costs vs profit, ROI tracking
- `docs/business-operations/financial-tracking.md` — Invoicing, expenses, taxes
- `docs/02-websites-playbook/maintenance.md` — Recurring revenue from maintenance

## Domain: Scaling & Growth

**Triggers:** scale, grow, hire, team, agency, phase, contractor, expand

**Quick ref:** [scaling-quick-ref.md](scaling-quick-ref.md) (start here for phases)

**Primary files:**

- `docs/business-operations/scaling.md` — 5-phase roadmap, hiring, team structure
- `docs/02-websites-playbook/scaling.md` — Website-specific growth timeline
- `docs/business-operations/time-management.md` — Time allocation for scaling
- `docs/02-websites-playbook/upsells-retainers.md` — Growing revenue per client

## Domain: Technical Delivery

**Triggers:** build, code, prompt, workflow, debug, test, deploy, quality, SEO, performance

**Primary files:**

- `docs/05-delivery-system/workflow/README.md` — Development phases overview
- `docs/05-delivery-system/prompting/README.md` — AI prompting techniques
- `docs/05-delivery-system/quality-standards/README.md` — Quality gates, standards
- `docs/05-delivery-system/troubleshooting/README.md` — Debugging & recovery
- `docs/05-delivery-system/context-management/README.md` — Context optimization

**Deep dives (load only when specific topic needed):**

- `docs/05-delivery-system/quality-standards/performance-deep-dive.md`
- `docs/05-delivery-system/quality-standards/security-deep-dive.md`
- `docs/05-delivery-system/quality-standards/testing-deep-dive.md`
- `docs/05-delivery-system/quality-standards/ux-deep-dive.md`

## Domain: Tooling & Tech Stack

**Triggers:** tool, IDE, MCP, provider, agent, Cloudflare, Astro, hosting

**Primary files:**

- `docs/06-tooling/README.md` — Tool categories overview
- `docs/06-tooling/coding-agents/README.md` — AI coding agents (Claude, AMP, OpenCode)
- `docs/06-tooling/providers/choosing-your-provider.md` — API provider comparison
- `docs/07-tech-stack/core-technologies.md` — Astro, Tailwind, recommended stack
- `docs/07-tech-stack/hosting/README.md` — Cloudflare ecosystem overview

## Domain: Legal & Compliance

**Triggers:** contract, legal, IP, license, terms, compliance, agreement

**Primary files:**

- `docs/legal/README.md` — Legal framework overview
- `docs/legal/ai-services-terms.md` — AI service terms for clients
- `docs/legal/ai-generated-content.md` — IP and content ownership

## Domain: Project Funding (this project, NOT client income)

**Triggers:** sponsor, patron, donate, fund, support, contribute, open-source

**Primary files:**

- `docs/project-funding/README.md` — Funding strategy overview
- `docs/project-funding/github-sponsors.md` — GitHub Sponsors program
- `docs/project-funding/supporter-program.md` — Patreon/Ko-fi tiers
- `docs/project-funding/affiliate-marketing.md` — Affiliate programs
- `docs/project-funding/digital-products.md` — Courses, templates, products
- `docs/project-funding/consulting-services.md` — Workshop & consulting rates

## Domain: Case Studies & Portfolio

**Triggers:** case study, portfolio, testimonial, document project, ROI analysis

**Primary files:**

- `docs/case-studies/README.md` — Case study framework
- `docs/case-studies/templates/website-project.md`
- `docs/case-studies/templates/automation-project.md`
- `docs/case-studies/templates/micro-saas-project.md`
- `docs/case-studies/templates/roi-analysis.md`

## Large Files Reference

Files over 800 lines — use selective reading (target specific H2 headings):

| File | Lines | When to Read |
| ---- | ----- | ------------ |
| `05-delivery-system/prompting/task-specific-patterns.md` | 1892 | Match by task type (feature/refactor/debug/test) |
| `05-delivery-system/quality-standards/seo.md` | 1874 | SEO-specific questions only |
| `05-delivery-system/quality-standards/performance.md` | 1839 | Performance optimization only |
| `05-delivery-system/context-management/README.md` | 1809 | Context strategy questions only |
| `05-delivery-system/troubleshooting/README.md` | 1573 | Match by error type |
| `business-operations/scaling.md` | 1090 | Match by phase number |

## Exclusions

Never retrieve from these paths:

- `docs/_archive/*` — Deprecated content
- `docs/appendix/contributing.md` — Internal process
- `docs/appendix/contribution-review.md` — Internal process
- `docs/appendix/contribution-levels.md` — Internal process
