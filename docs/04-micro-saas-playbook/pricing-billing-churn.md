# Pricing, Billing & Churn

> The business mechanics that determine whether your SaaS makes money.

## Pricing Tiers

### Start Simple

Launch with 1-2 tiers. You don't have enough data to know what customers need.

**Two-tier example:**
- **Starter** — $29/month, core features, limits on usage
- **Pro** — $79/month, higher limits, priority support

### Add Tiers Based on Data

After 20+ customers, you'll see patterns:
- Some users hit limits constantly → need a higher tier
- Some barely use it → maybe a cheaper tier makes sense
- Power users want features you don't have → premium tier opportunity

### Annual Discounts

Offer 2 months free for annual payment (17% discount). Benefits:
- Cash upfront
- Lower churn (committed for a year)
- Better unit economics

---

## Billing Setup

### Use Stripe for Everything

Don't reinvent billing. Stripe handles:
- Subscriptions (monthly/annual)
- Failed payment retries
- Invoices and receipts
- Tax compliance (Stripe Tax)
- Customer portal (self-service)

### Flat Rate vs Usage-Based

**Flat rate** (most micro-SaaS):
- Simple to understand
- Predictable revenue
- Best for tools with consistent value

**Usage-based** (API products, high-variance tools):
- Aligns cost with value delivered
- Better for customers with variable needs
- More complex to implement

Start flat rate unless your product is inherently usage-based.

### Free Trials vs Freemium

**Free trial** (recommended for most):
- 7-14 days, full access
- Requires payment method upfront (higher conversion)
- Clear end date creates urgency

**Freemium**:
- Limited features forever
- Works if free users help growth (network effects, viral)
- Risky—most free users never convert

---

## Churn Control

Churn kills SaaS. 5% monthly churn = 46% annual churn. You're constantly replacing half your customers.

### Cancellation Flow

When someone cancels:
1. **Ask why** — Short survey (too expensive, missing features, not using it, switching to competitor)
2. **Offer pause** — "Take a break for 1-3 months instead of canceling"
3. **Offer downgrade** — Cheaper tier to keep them
4. **Make it easy** — Don't be scummy. Let them leave with dignity.

### Win-Back Emails

30 days after cancellation:
- "We've added [feature they wanted]"
- "Here's 20% off if you come back"
- "We'd love feedback on what we could improve"

### Reduce Involuntary Churn

Failed payments cause 20-40% of churn. Use:
- **Stripe's smart retries** — Automatic retry at optimal times
- **Dunning emails** — "Your payment failed, update your card"
- **Grace period** — Don't cut access immediately

---

## Metrics to Track

Focus on these four. Everything else is noise at small scale.

### MRR (Monthly Recurring Revenue)
Your total monthly subscription revenue. The number that matters most.

Track: New MRR, churned MRR, expansion MRR, net MRR change.

### Churn Rate
Percentage of customers who cancel each month.

Formula: (Customers lost this month / Customers at start of month) × 100

Target: Under 5% monthly for B2B micro-SaaS.

### LTV (Lifetime Value)
How much a customer pays over their lifetime.

Simple formula: Average monthly revenue per customer × Average customer lifespan (months)

### CAC (Customer Acquisition Cost)
How much you spend to acquire one customer.

Formula: Total marketing spend / New customers acquired

**The rule:** LTV should be at least 3× CAC. If you spend $50 to acquire a customer, they should pay you at least $150 over their lifetime.

---

## When to Raise Prices

### Good Reasons to Raise

- **New features added** — More value = higher price
- **Value proven** — Customers tell you it's saving them hours/money
- **Demand exceeds capacity** — Price is a filter
- **You're the cheapest option** — Usually means you're underpriced

### How to Raise

1. **Grandfather existing customers** — Keep their price locked (or give long notice)
2. **Announce in advance** — 30-60 days for existing, immediate for new
3. **Explain the value** — New features, improved product, continued development

### Pricing Psychology

- $29 feels like "professional tool"
- $9 feels like "might be low quality"
- $99+ requires serious ROI justification
- Annual pricing should show monthly equivalent ("$49/mo billed annually")

---

## Bottom Line

Pricing is a lever, not a lock. Start somewhere reasonable, then adjust based on data. The right price is the one that maximizes revenue while minimizing churn.

Most first-time founders underprice. If no one complains about your price, it's too low.
