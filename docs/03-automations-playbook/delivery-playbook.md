# Delivery Playbook

Step-by-step process for delivering automation projects.

---

## Phase 1: Discovery (1-2 Hours)

### Map Current Workflow
Ask the client to walk you through their process:
- "Show me exactly what happens when a lead comes in"
- "What do you click? What do you copy/paste?"
- "Where does this data end up?"

Record it. Screen share recording is gold.

### Identify Pain Points
- Where do things slow down?
- What gets forgotten?
- What causes errors?
- What do they hate doing?

### Define Success Criteria
Get specific, measurable outcomes:
- "Lead response time under 5 minutes" ✓
- "Faster lead handling" ✗

### Document Integrations Needed
List every tool involved:
- CRM (HubSpot, Salesforce, etc.)
- Email (Gmail, Outlook)
- Spreadsheets (Google Sheets, Airtable)
- Communication (Slack, Teams)
- Payment (Stripe, QuickBooks)

Check API availability for each.

---

## Phase 2: Design (1-2 Hours)

### Flowchart the Automation
Create a visual diagram showing:
1. Trigger (what starts it)
2. Steps (what happens in sequence)
3. Decision points (if/then logic)
4. Outputs (where data goes)
5. Error handling (what if something fails)

Tools: Whimsical, Miro, even hand-drawn works.

### Identify Edge Cases
Walk through scenarios:
- What if the form is incomplete?
- What if the email bounces?
- What if two requests come in simultaneously?
- What if the API is down?

Document how each is handled.

### Get Client Sign-Off
Send the flowchart with written summary:
- "Here's what we're building"
- "Here's what it won't handle"
- "Here's what you need to provide"

Get explicit approval before building.

---

## Phase 3: Build (1-2 Weeks)

### Set Up Tools
- Create accounts (n8n, Make, Zapier)
- Set up authentication for integrations
- Create test/staging environment

### Build Core Workflow
Start with the happy path—everything works perfectly.

Build in this order:
1. Trigger working
2. First action working
3. Each subsequent step
4. Final output confirmed

Test after every addition.

### Add Error Handling
For each step:
- What if it fails?
- Retry logic (how many times, how long to wait)
- Fallback action (notify someone, log error)
- Error notifications (Slack, email)

### Test with Sample Data
- Create realistic test cases
- Run through full workflow
- Check outputs match expectations
- Test edge cases from Phase 2

---

## Phase 4: Testing (2-3 Days)

### Client UAT (User Acceptance Testing)
Give client access to test:
- "Submit a test lead with these details"
- "Check if it appears in your CRM correctly"
- "Verify the email looks right"

### Edge Case Testing
Run through every scenario documented:
- Incomplete data
- Duplicate submissions
- Large volumes
- Special characters
- Timezone issues

### Performance Check
- How fast does it run?
- Any rate limit concerns?
- What's the cost per execution?
- Will it scale to expected volume?

---

## Phase 5: Handoff

### Documentation
Create a simple doc covering:
- What the automation does
- How to trigger it manually (if applicable)
- What to check if something seems wrong
- Who to contact for issues

Keep it short. Nobody reads long docs.

### Training Session
30-60 minute call:
- Walk through the automation live
- Show them the dashboard/logs
- Demonstrate common scenarios
- Answer questions

Record it for their team.

### Support Period
Define what's included post-launch:
- "2 weeks of bug fixes included"
- "Response within 24 hours for critical issues"
- "Monthly retainer available for ongoing support"

---

## Delivery Checklist

Before calling it done:

- [ ] All success criteria met
- [ ] Error handling tested
- [ ] Client has tested and approved
- [ ] Documentation complete
- [ ] Training session recorded
- [ ] Monitoring/alerts set up
- [ ] Support terms clear
- [ ] Final invoice sent

---

## Common Delivery Issues

### Scope Creep
Client: "Can it also do X?"

Response: "That's a great idea. Let's add it to phase 2. For now, let's get the core automation live."

### Integration Doesn't Work as Expected
API docs lie. Always prototype integrations early. If it won't work, you want to know in Phase 2, not Phase 3.

### Client Can't Test
They're busy. Set a deadline: "I need your testing feedback by Friday or we push the launch."

### "It's Not Working"
99% of the time: user error or changed input format.

First question: "Can you show me exactly what you did?"
