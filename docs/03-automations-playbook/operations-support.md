# Operations & Support

Managing automation clients after delivery.

---

## Monitoring

### Error Notifications
Set up alerts for every automation:
- Failed executions → Slack/email to you
- Threshold alerts (error rate > 5%)
- Integration auth failures

Don't wait for clients to report issues.

### Health Checks
Weekly (complex automations):
- Review error logs
- Check execution counts
- Verify outputs look correct

Monthly (simple automations):
- Quick log review
- Spot check recent executions

### Performance Metrics
Track and report:
- Executions per period
- Success rate
- Average processing time
- Cost per execution

Share monthly with client. Shows value.

---

## Client Training

### Documentation Standards
Every automation needs:
1. One-page overview (what it does, when it runs)
2. Troubleshooting guide (common issues, quick fixes)
3. Escalation path (when to contact you)

Keep it visual. Screenshots > paragraphs.

### Video Walkthroughs
Record Loom videos:
- "Here's how to check if it ran"
- "Here's how to retry a failed execution"
- "Here's what this error means"

Link videos in documentation.

### Self-Serve vs Contact You
Teach clients what they can handle:

**Self-Serve:**
- Checking execution history
- Retrying failed runs
- Updating templates/content

**Contact You:**
- Adding new fields
- Changing logic
- Integration errors
- "It's completely broken"

---

## Common Issues

### API Changes
Platforms update without warning. Automations break.

**Prevention:** Follow changelogs for critical integrations.  
**Response:** Fix immediately, notify client, document what changed.

### Rate Limits
High-volume automations hit API limits.

**Prevention:** Build in delays, batch processing.  
**Response:** Implement queuing, negotiate higher limits, or upgrade client's plan.

### Data Format Changes
Client changes their form, spreadsheet columns, or CRM fields.

**Prevention:** Document expected formats. Alert client that changes need coordination.  
**Response:** Update field mappings, test thoroughly.

### Auth Token Expiry
OAuth tokens expire. Integrations stop working.

**Prevention:** Use refresh tokens, monitor for auth failures.  
**Response:** Re-authenticate, set calendar reminder for next expiry.

---

## Sunsetting Automations

### When Client Outgrows You
Signs it's time:
- They hire an ops/dev team
- Volume exceeds your tooling
- They want custom software, not no-code

This is good. Don't cling.

### Handoff Process
1. **Document everything** - Full technical documentation
2. **Knowledge transfer** - 2-3 sessions with their team
3. **Transition period** - 30-60 days of support during handoff
4. **Clean break** - Transfer all accounts and credentials

### Exit Checklist
- [ ] All credentials transferred
- [ ] Documentation complete
- [ ] Their team can operate independently
- [ ] Final invoice paid
- [ ] Accounts removed from your access
- [ ] Testimonial/referral requested

---

## Scaling Your Operations

### When to Systematize
- 5+ active retainer clients
- Spending more time monitoring than building
- Missing issues before clients report them

### Systems to Build
- Central monitoring dashboard
- Standardized onboarding checklist
- Template documentation
- Monthly reporting automation (yes, automate your own reporting)

### When to Hire
- 10+ retainer clients
- Can't take new projects
- Support eating into build time

First hire: Part-time ops person to handle monitoring and Tier 1 support.
