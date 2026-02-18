---
doc_type: playbook
domain: pricing
streams: [micro-saas]
keywords: [pricing, scoping, replacement, time-value, subscription]
related_docs:
  - 01-money-map/pricing-fundamentals.md
  - 02-websites-playbook/pricing-economics.md
  - 03-automations-playbook/pricing-automations.md
token_estimate: 1600
---

# Scoping & Pricing

> Build the smallest thing that solves the problem. Charge based on value.

## Scoping: Less Is More

The #1 mistake: building too much.

### The Rule of One

Your Micro-SaaS should have:
- **One user type** (or two: admin + end user)
- **One core action** (book, track, quote, notify)
- **One screen** that does 90% of the work

### Example: Booking System

**Too much:**
- Calendar sync
- Payment processing
- Customer accounts
- Email campaigns
- Analytics dashboard
- Multi-location support

**Just right:**
- Admin sets available slots per day
- Clients see available slots, pick one
- Admin sees all bookings
- Email/SMS notification on booking

That's it. Build that. Add features only if client pays for them.

### Scoping Questions

Ask yourself:

1. What's the ONE thing this must do?
2. What can the client keep doing manually? (Don't automate everything)
3. What's the simplest UI that works?
4. Can I build this in 1-2 days?

If it takes more than 2 days to build, you're over-scoping.

## Proposal Structure

Keep it simple. One page max.

```
[TOOL NAME] — Simple [what it does]

THE PROBLEM:
You currently [pain point]. This costs you [time/money].

THE SOLUTION:
I'll build [simple description]:
• [Core feature 1]
• [Core feature 2]
• [Core feature 3]

WHAT YOU GET:
• Hosted solution (no tech hassle)
• Mobile-friendly
• Training session
• [X] months of support included

PRICING:
Option A: $[setup] one-time + $[monthly]/month
Option B: $[higher monthly]/month (no setup fee)

TIMELINE:
[X] days from approval

WHAT'S NOT INCLUDED:
• [Feature they might expect but isn't in scope]
• Additional features quoted separately
```

## Pricing Strategies

### Strategy 1: Replacement Pricing

What do they pay now? Price under that.

| Current Tool | Their Cost | Your Price | Their Savings |
|-------------|-----------|-----------|---------------|
| Acuity | $25/mo | $75/mo | -$50 (but simpler, custom) |
| Calendly Pro | $16/mo | $50/mo | -$34 (but tailored exactly) |
| Square Appointments | $29/mo | $100/mo | -$71 (but no transaction fees) |

Wait — negative savings? Yes, sometimes your tool costs more because:
- It's exactly what they need (no bloat)
- You provide support (they know you)
- It integrates with their existing setup
- No learning curve

### Strategy 2: Time-Value Pricing

Calculate time saved → price at fraction of that.

**Example:**
- Client spends 5 hours/week on manual booking
- Their time is worth $50/hour
- That's $250/week = $1,000/month in lost productivity
- Your tool costs $150/month
- They "save" $850/month (or get 5 hours back)

### Strategy 3: Setup + Monthly

Most common model:

| Component | What It Covers | Typical Range |
|-----------|---------------|---------------|
| Setup fee | Building, customization, training | $500-2,000 |
| Monthly fee | Hosting, support, updates | $50-200/month |

**When to use:** When you want upfront payment for build time.

### Strategy 4: Monthly Only

No setup fee, higher monthly.

| Scenario | Monthly Price |
|----------|--------------|
| Simple tool | $100-150/month |
| Medium complexity | $200-300/month |
| Complex (rare) | $400-500/month |

**When to use:** When client prefers predictable expenses, no large upfront.

### Strategy 5: Annual Discount

Offer 10-15% off for annual payment.

> "You can pay $150/month or $1,500/year (save $300)."

Gets you cash upfront. Reduces churn risk.

## Handling Objections

### "That seems expensive for something so simple"

> "It's simple because that's exactly what you need. Complex tools cost more and take longer to use. You're paying for a solution that fits, not features you'll never touch."

### "Can't you just add [feature]?"

> "I can. That would add $[X] to the setup and $[Y]/month. Want me to update the proposal?"

Never add scope for free. Every feature has a price.

### "My nephew could build this"

> "Possibly. The difference is I'll build it in [X] days, host it, maintain it, and fix things when they break. You'll have my number when something goes wrong."

### "What if I need changes later?"

> "Small changes (colors, text, minor tweaks) are included. Feature additions are quoted separately — I'll always give you a price before doing the work."

## Contract Essentials

Keep it brief. Include:

1. **Scope** — Exactly what you're building
2. **Price** — Setup and monthly
3. **Timeline** — When it's delivered
4. **Payment terms** — When they pay (50% upfront common)
5. **What's not included** — Prevent scope creep
6. **Support terms** — Response time, what's covered
7. **Exit clause** — What happens if they cancel

## After They Say Yes

1. Get payment (50% upfront or first month + setup)
2. Set kickoff date
3. Gather any assets/info needed
4. Build (see [Building Tiny](building-tiny.md))
5. Deploy and train
6. Start monthly billing

---

**Next**: [Building Tiny](building-tiny.md) — How to build fast and stay profitable.
