# MVP Build System

> Build fast, learn fast, iterate fast. The goal is learning, not perfection.

## The Thin Vertical Slice

Build one user flow, end to end. Not a wide, shallow prototype—a narrow, complete experience.

**What this means:**
- One user type (not multiple roles)
- One core workflow (not all planned features)
- Complete journey (sign up → core value → payment)
- Happy path only (edge cases come later)

**Example:**
Building an invoice tool? Your MVP is:
1. User signs up
2. Creates one invoice
3. Sends it
4. Gets paid (Stripe integration)

Not: templates, recurring invoices, multiple currencies, team accounts, expense tracking.

---

## MVP Constraints

### Time Constraint
**Max 2 weeks to launch.** After validation, you should have paying customers waiting. Don't make them wait months.

### Feature Constraint
**Max 5 core features.** Everything else is a "nice to have" that you'll add based on real user feedback.

### Perfection Constraint
**Ship at 80%.** Your MVP will feel embarrassing. That's correct. If it doesn't, you waited too long.

---

## Tech Stack for Speed

Optimize for shipping, not scalability. You can refactor later (and you probably won't need to).

### Frontend
- **Astro** or **Next.js** — Fast to build, good ecosystem
- **Tailwind CSS** — No custom CSS debates
- **shadcn/ui** — Copy-paste components, not library lock-in

### Backend
- **Cloudflare Workers** — Zero cold starts, generous free tier
- **D1 or Turso** — SQLite at the edge, simple
- **Supabase** — If you need real-time or complex queries

### Authentication
- **Clerk** — Done in 30 minutes, handles everything
- **Auth.js** — If you want more control
- **Supabase Auth** — If already using Supabase

### Payments
- **Stripe** — No alternatives worth considering for MVP
- Use Stripe Checkout — Don't build custom payment forms
- Stripe Billing for subscriptions

### Hosting
- **Vercel** — Next.js native, simple
- **Cloudflare Pages** — Cheaper at scale
- **Railway** — If you need a traditional server

---

## What to Skip Initially

These feel important. They're not. Add them after you have 10+ paying users.

### Skip: Fancy Onboarding
Users who paid in advance are motivated. A simple "here's how it works" page is enough.

### Skip: Admin Dashboards
Use your database directly. Drizzle Studio, Prisma Studio, or raw SQL. You don't need a custom admin panel for 20 users.

### Skip: Multiple User Roles
Everyone is an admin. Add roles when a customer actually needs team features.

### Skip: Email Automation
Transactional emails (receipts, password resets) only. Marketing sequences can wait.

### Skip: Analytics Beyond Basics
Plausible or simple page views. You don't need Mixpanel funnels for 15 users—talk to them directly.

### Skip: Perfect Error Handling
Log errors. Fix them when they happen. Don't anticipate every edge case.

---

## What to Nail

These actually matter for your first paying users.

### Core Value Proposition
The one thing your product does. It must work reliably. This is why people paid.

### Payment Flow
Stripe Checkout → Webhook → Activate account. Test it. Test it again. Nothing kills trust like broken payments.

### Basic Onboarding
User signs up → immediately sees how to get value → accomplishes first task in under 2 minutes.

### Responsive Email Support
You're small. Use that. Reply to every email within hours. This is your competitive advantage over big players.

---

## MVP Development Flow

```
Day 1-2:   Database schema, auth setup
Day 3-5:   Core feature implementation
Day 6-7:   Payment integration
Day 8-10:  Basic UI polish, onboarding
Day 11-12: Testing, bug fixes
Day 13-14: Deploy, notify waiting customers
```

Two weeks. Tight, but achievable with vibecoding.

---

## After Launch

Your MVP is live. Now what?

1. **Watch real usage.** What do people actually do? What confuses them?
2. **Talk to every user.** Ask what's missing, what's broken, what's confusing.
3. **Fix what's broken.** Bugs before features.
4. **Add one feature at a time.** Based on requests, not assumptions.
5. **Raise prices for new users.** You probably undercharged.

---

## Bottom Line

The MVP isn't the product—it's a hypothesis. You're testing whether people will pay for this solution to this problem.

Build the smallest thing that tests that hypothesis. Everything else is procrastination disguised as progress.
