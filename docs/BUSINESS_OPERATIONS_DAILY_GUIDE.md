# Business Operations Daily Guide

A comprehensive guide to running successful daily business operations using Fabric patterns.

---

## Table of Contents

1. [Daily Workflow Overview](#daily-workflow-overview)
2. [Morning Routine (30-45 min)](#morning-routine-30-45-min)
3. [Prospecting Block (1-2 hours)](#prospecting-block-1-2-hours)
4. [Outreach Block (1-2 hours)](#outreach-block-1-2-hours)
5. [Sales Block (1-2 hours)](#sales-block-1-2-hours)
6. [Client Work Block (2-4 hours)](#client-work-block-2-4-hours)
7. [End of Day Review (15-30 min)](#end-of-day-review-15-30-min)
8. [Weekly Operations](#weekly-operations)
9. [Monthly Operations](#monthly-operations)
10. [Metrics Dashboard](#metrics-dashboard)
11. [Troubleshooting Common Issues](#troubleshooting-common-issues)

---

## Daily Workflow Overview

```
┌─────────────────────────────────────────────────────────────────┐
│                    DAILY OPERATIONS FLOW                        │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  MORNING (30-45 min)                                           │
│  ├── Inbox triage (classify_email_reply)                       │
│  ├── Lead scoring (flag_hot_lead)                              │
│  └── Priority queue setup                                       │
│                                                                 │
│  PROSPECTING (1-2 hrs)                                         │
│  ├── Find prospects (scrape_local_businesses)                  │
│  └── Analyze gaps (analyze_business_gaps)                      │
│                                                                 │
│  OUTREACH (1-2 hrs)                                            │
│  ├── Personalize (personalize_from_gaps)                       │
│  ├── Draft emails (draft_cold_email)                           │
│  └── Queue follow-ups (draft_followup_sequence)                │
│                                                                 │
│  SALES (1-2 hrs)                                               │
│  ├── Respond to leads (draft_reply)                            │
│  ├── Qualify opportunities (qualify_leads)                     │
│  └── Create proposals (create_winning_proposal)                │
│                                                                 │
│  CLIENT WORK (2-4 hrs)                                         │
│  ├── Deliver services                                          │
│  ├── Website audits (audit_business_website)                   │
│  └── Automation setup (automate_task)                          │
│                                                                 │
│  EOD REVIEW (15-30 min)                                        │
│  ├── Update CRM                                                │
│  ├── Log metrics                                               │
│  └── Plan tomorrow                                             │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

---

## Morning Routine (30-45 min)

### Step 1: Inbox Triage (15 min)

Process all overnight emails to identify urgent opportunities.

```bash
# For each new email, classify it
cat email.txt | fabric -p classify_email_reply > classified.txt

# Batch process multiple emails
for email in inbox/*.txt; do
  fabric -p classify_email_reply < "$email" >> morning_triage.txt
done
```

**Action Matrix:**

| Classification | Action | Timing |
|----------------|--------|--------|
| INTERESTED | Move to sales block | Today |
| QUESTION | Draft response | Today |
| OBJECTION | Prepare handling | Today |
| NOT_INTERESTED | Archive + learn | End of day |
| AUTO_REPLY | Flag for follow-up | 3-5 days |
| SPAM | Delete | Immediately |

### Step 2: Lead Scoring (10 min)

Score all interested/question leads to prioritize your day.

```bash
# Score each promising lead
cat interested_lead.txt | fabric -p flag_hot_lead > lead_score.txt
```

**Priority Queue:**

| Tier | Today's Capacity | Response Window |
|------|------------------|-----------------|
| HOT (75-100) | All of them | Within 1 hour |
| WARM (50-74) | Top 5 | Within 4 hours |
| NURTURE (25-49) | Add to sequence | Within 24 hours |

### Step 3: Plan Your Day (5-10 min)

Based on morning triage:

1. **Block calendar** for HOT lead responses
2. **Queue WARM leads** for sales block
3. **Schedule automation** for NURTURE leads
4. **Identify prospecting** needs (if pipeline is light)

**Daily Targets:**
- 3-5 HOT lead responses
- 10-20 new cold emails sent
- 1-2 proposals created
- 50+ prospects identified (if prospecting day)

---

## Prospecting Block (1-2 hours)

### When to Prospect

- Pipeline has < 50 active leads
- Closing rate dropping
- Need new market/vertical
- Monday/Wednesday focus

### Workflow

```bash
# Step 1: Identify prospects in a vertical/location
echo "Find plumbers in Austin, TX without online booking" | \
  fabric -p scrape_local_businesses > prospects.txt

# Step 2: Analyze top prospects' gaps
for prospect in top_prospects/*.txt; do
  fabric -p analyze_business_gaps < "$prospect" >> gap_analyses.txt
done
```

### Daily Prospecting Targets

| Activity | Target | Time |
|----------|--------|------|
| New businesses identified | 50-100 | 30 min |
| Gap analyses completed | 10-20 | 45 min |
| Prospects tiered and CRM'd | All | 15 min |

### Prospecting SOP

1. **Choose vertical** (plumbers, dentists, lawyers, etc.)
2. **Choose location** (your city or target market)
3. **Define gap** (no website, no reviews, no booking)
4. **Run scrape_local_businesses** with search results
5. **Tier results** (1=hot, 2=warm, 3=nurture)
6. **Run analyze_business_gaps** on Tier 1 prospects
7. **Export to CRM** with notes

### Prospecting Tips

- **Best days:** Monday, Wednesday (people are in work mode)
- **Best sources:** Google Maps, Yelp, industry directories
- **Focus on:** Businesses with 4+ stars but weak websites
- **Avoid:** Chains, franchises, businesses with strong digital presence

---

## Outreach Block (1-2 hours)

### Workflow

```bash
# Step 1: Create personalized copy from gap analysis
cat gap_analysis.txt | fabric -p personalize_from_gaps > copy_kit.txt

# Step 2: Draft cold email
echo "Business: Acme Plumbing
Gap: No online booking
Location: Austin, TX
Selling: AI booking assistant" | fabric -p draft_cold_email > email.txt

# Step 3: Create follow-up sequence
cat original_email.txt | fabric -p draft_followup_sequence > sequence.txt
```

### Daily Outreach Targets

| Activity | Target | Time |
|----------|--------|------|
| Personalization kits created | 10-15 | 20 min |
| Cold emails drafted | 10-15 | 30 min |
| Follow-up sequences queued | 10-15 | 20 min |
| Emails sent | 20-30 | 10 min |

### Outreach SOP

1. **Batch personalization:** Run personalize_from_gaps on all gap analyses
2. **Batch drafting:** Run draft_cold_email on all prospects
3. **Review and edit:** Quick 30-second review of each email
4. **Schedule sending:** Use email tool to spread sends across day
5. **Queue follow-ups:** Load follow-up sequences into automation

### Outreach Timing

| Day | Best Send Times | Notes |
|-----|-----------------|-------|
| Tuesday | 8-10am, 2-4pm | Highest open rates |
| Wednesday | 8-10am, 2-4pm | Second best |
| Thursday | 8-10am | Before weekend mode |
| Monday | 10am-12pm | After morning meetings |
| Friday | Avoid | Low engagement |

### Email Sending Rules

- **Max per day:** 50 (new domain) → 100 (warmed) → 200 (established)
- **Spacing:** 2-5 minutes between sends
- **Reply rate goal:** 5-10%
- **Open rate goal:** 20-40%

---

## Sales Block (1-2 hours)

### Workflow

```bash
# Step 1: Draft replies to interested leads
cat lead_email.txt | fabric -p draft_reply > reply.txt

# Step 2: Qualify serious opportunities
cat opportunity.txt | fabric -p qualify_leads > qualification.txt

# Step 3: Create proposal for qualified leads
cat qualified_lead.txt | fabric -p create_winning_proposal > proposal.txt
```

### Daily Sales Targets

| Activity | Target | Time |
|----------|--------|------|
| Lead responses sent | 5-10 | 30 min |
| Discovery calls booked | 1-3 | - |
| Leads qualified | 3-5 | 20 min |
| Proposals created | 1-2 | 30 min |
| Proposals sent | 1-2 | 10 min |

### Sales SOP

1. **Respond to HOT leads** within 1 hour of classification
2. **Book discovery calls** as primary CTA
3. **Qualify during discovery** using BANT framework
4. **Create proposal** within 24 hours of discovery call
5. **Follow up on proposals** at 3, 7, 14 days

### Discovery Call Framework

```
1. Build rapport (2 min)
2. Understand their situation (10 min)
   - What prompted them to respond?
   - What's the current problem?
   - What have they tried?
3. Qualify (5 min)
   - Budget range?
   - Decision timeline?
   - Who else is involved?
4. Present solution (10 min)
5. Handle objections (5 min)
6. Close or next step (3 min)
```

### Proposal Best Practices

- Send within 24 hours of call
- Include 3 pricing tiers
- Lead with their words/problems
- Quantify ROI
- Make next step crystal clear

---

## Client Work Block (2-4 hours)

### Delivery Workflows

#### Website Audit Delivery
```bash
# Generate comprehensive audit
echo "https://clientwebsite.com
Business: Client Name
Type: Plumber
Location: Austin, TX" | fabric -p audit_business_website > audit_report.txt
```

#### Automation Delivery
```bash
# Generate automation script for client
echo "Task: Automatically organize invoices by date
OS: Mac
Schedule: Daily at 9pm" | fabric -p automate_task > invoice_organizer.sh
```

#### Lead Guardian Setup
```bash
# Design AI agent for client
cat client_business_details.txt | fabric -p create_lead_guardian > agent_config.txt
```

### Client Work SOP

1. **Review deliverables** from yesterday
2. **Check client communications** for urgent requests
3. **Execute planned work** per project timeline
4. **Document progress** in project management tool
5. **Send updates** to clients (at least weekly)

### Time Allocation

| Activity | % of Block | Hours |
|----------|------------|-------|
| Active delivery | 70% | 1.5-3 |
| Client communication | 15% | 20-40 min |
| Documentation | 15% | 20-40 min |

---

## End of Day Review (15-30 min)

### Daily Metrics to Track

```
┌──────────────────────────────────────────────────────┐
│              DAILY METRICS TRACKER                   │
├──────────────────────────────────────────────────────┤
│ PROSPECTING                                          │
│ ├── Prospects identified: ___                        │
│ ├── Gap analyses completed: ___                      │
│ └── Added to CRM: ___                                │
│                                                      │
│ OUTREACH                                             │
│ ├── Emails sent: ___                                 │
│ ├── Opens: ___                                       │
│ ├── Replies: ___                                     │
│ └── Open rate: ___% | Reply rate: ___%              │
│                                                      │
│ SALES                                                │
│ ├── Leads responded to: ___                          │
│ ├── Calls booked: ___                                │
│ ├── Calls completed: ___                             │
│ ├── Proposals sent: ___                              │
│ └── Deals closed: ___                                │
│                                                      │
│ REVENUE                                              │
│ ├── Revenue booked: $___                             │
│ ├── Pipeline value: $___                             │
│ └── Win rate: ___%                                   │
└──────────────────────────────────────────────────────┘
```

### EOD Checklist

- [ ] All HOT leads responded to
- [ ] CRM updated with all activities
- [ ] Follow-ups scheduled for tomorrow
- [ ] Proposals sent where promised
- [ ] Client work delivered on time
- [ ] Metrics logged
- [ ] Tomorrow's priority list created

### Planning Tomorrow

1. Check calendar for calls/meetings
2. Review email queue for responses needed
3. Check follow-up sequences for replies
4. Identify if prospecting block is needed
5. Block time for proposals due

---

## Weekly Operations

### Monday: Pipeline Review

```bash
# Generate financial model update if needed
cat current_metrics.txt | fabric -p build_financial_model > weekly_forecast.txt
```

- Review pipeline health
- Update forecasts
- Plan week's activities
- Set weekly targets

### Tuesday-Thursday: Execution

- Focus on daily workflow
- Maximum prospecting/outreach
- All sales activities

### Friday: Admin & Strategy

```bash
# Review pricing if needed
cat current_pricing.txt | fabric -p optimize_pricing_strategy > pricing_review.txt
```

- Send weekly client updates
- Review week's metrics
- Plan next week
- Administrative tasks

### Weekly Targets

| Metric | Target | Your Goal |
|--------|--------|-----------|
| Prospects identified | 200-400 | ___ |
| Cold emails sent | 100-150 | ___ |
| Replies received | 10-20 | ___ |
| Calls booked | 5-10 | ___ |
| Proposals sent | 2-5 | ___ |
| Deals closed | 1-2 | ___ |

---

## Monthly Operations

### Week 1: Analysis

- Review prior month metrics
- Analyze conversion rates by stage
- Identify bottlenecks
- Update ICPs if needed

### Week 2-3: Optimization

```bash
# If funnel needs work
cat funnel_data.txt | fabric -p build_sales_funnel > funnel_optimization.txt

# If lead magnet needs refresh
cat audience_data.txt | fabric -p generate_lead_magnet > new_lead_magnet.txt
```

### Week 4: Planning

- Set next month's targets
- Plan content/campaigns
- Review and clean CRM
- Update automation sequences

### Monthly Targets

| Metric | Starter | Growth | Scale |
|--------|---------|--------|-------|
| Revenue | $5-10K | $20-50K | $100K+ |
| New clients | 2-4 | 5-10 | 15+ |
| Pipeline value | $30K | $100K | $300K+ |
| Win rate | 20%+ | 30%+ | 40%+ |

---

## Metrics Dashboard

### Key Performance Indicators

```
┌─────────────────────────────────────────────────────────────────┐
│                    BUSINESS HEALTH DASHBOARD                    │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  ACQUISITION METRICS                                            │
│  ├── Cost per Lead (CPL): $___                                 │
│  ├── Cost per Meeting (CPM): $___                              │
│  └── Customer Acquisition Cost (CAC): $___                     │
│                                                                 │
│  CONVERSION METRICS                                             │
│  ├── Email Open Rate: ___% (target: 25%+)                      │
│  ├── Email Reply Rate: ___% (target: 5%+)                      │
│  ├── Lead to Meeting: ___% (target: 10%+)                      │
│  ├── Meeting to Proposal: ___% (target: 50%+)                  │
│  └── Proposal to Close: ___% (target: 30%+)                    │
│                                                                 │
│  REVENUE METRICS                                                │
│  ├── Average Deal Size: $___                                   │
│  ├── Monthly Recurring Revenue: $___                           │
│  ├── Lifetime Value (LTV): $___                                │
│  └── LTV:CAC Ratio: ___:1 (target: 3:1+)                       │
│                                                                 │
│  EFFICIENCY METRICS                                             │
│  ├── Revenue per Hour: $___                                    │
│  ├── Leads per Hour: ___                                       │
│  └── Proposals per Week: ___                                   │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

### Tracking Spreadsheet Setup

| Date | Prospects | Emails Sent | Opens | Replies | Calls | Proposals | Closed | Revenue |
|------|-----------|-------------|-------|---------|-------|-----------|--------|---------|
| Mon  |           |             |       |         |       |           |        |         |
| Tue  |           |             |       |         |       |           |        |         |
| Wed  |           |             |       |         |       |           |        |         |
| Thu  |           |             |       |         |       |           |        |         |
| Fri  |           |             |       |         |       |           |        |         |

---

## Troubleshooting Common Issues

### Low Reply Rates (<3%)

**Diagnose:**
```bash
# Re-analyze your targeting
cat failed_emails.txt | fabric -p analyze_business_gaps
```

**Fixes:**
1. Review subject lines (too generic?)
2. Check personalization quality
3. Verify you're reaching decision makers
4. Test different pain points
5. Improve proof/credibility

### Low Meeting Conversion (<5%)

**Diagnose:**
```bash
# Re-qualify your leads
cat low_converting_leads.txt | fabric -p qualify_leads
```

**Fixes:**
1. Better qualify before outreach
2. Improve discovery call script
3. Address objections earlier
4. Offer lower-commitment first step
5. Improve social proof

### Low Close Rate (<20%)

**Diagnose:**
```bash
# Review your pricing strategy
cat lost_deals.txt | fabric -p optimize_pricing_strategy
```

**Fixes:**
1. Improve proposal structure
2. Add case studies/social proof
3. Review pricing tiers
4. Follow up more aggressively
5. Address objections in proposal

### Pipeline Running Dry

**Diagnose:**
Review last week's prospecting volume

**Fixes:**
1. Increase daily prospecting targets
2. Add new lead sources
3. Try new verticals
4. Reactivate old leads
5. Ask for referrals

### Feeling Overwhelmed

**Fixes:**
1. Batch similar activities
2. Use automation more aggressively
3. Hire/outsource prospecting
4. Raise prices (fewer clients, same revenue)
5. Focus on highest-value activities

---

## Quick Reference Commands

```bash
# Morning Triage
cat email.txt | fabric -p classify_email_reply
cat lead.txt | fabric -p flag_hot_lead

# Prospecting
echo "Find [business type] in [location] without [feature]" | fabric -p scrape_local_businesses
cat business.txt | fabric -p analyze_business_gaps

# Outreach
cat gaps.txt | fabric -p personalize_from_gaps
cat prospect.txt | fabric -p draft_cold_email
cat original.txt | fabric -p draft_followup_sequence

# Sales
cat email.txt | fabric -p draft_reply
cat lead.txt | fabric -p qualify_leads
cat qualified.txt | fabric -p create_winning_proposal

# Delivery
echo "https://site.com" | fabric -p audit_business_website
echo "Task description" | fabric -p automate_task
cat business.txt | fabric -p create_lead_guardian

# Strategy
cat metrics.txt | fabric -p build_financial_model
cat pricing.txt | fabric -p optimize_pricing_strategy
cat plan.txt | fabric -p automate_business_plan
```

---

## Daily Success Checklist

### Non-Negotiables (Do Every Day)

- [ ] Process inbox with classify_email_reply
- [ ] Respond to all HOT leads within 1 hour
- [ ] Send at least 10 cold emails
- [ ] Update CRM with all activities
- [ ] Log daily metrics

### Growth Activities (Do Most Days)

- [ ] 30+ minutes of prospecting
- [ ] 1+ discovery call
- [ ] Follow up on open proposals
- [ ] Nurture warm leads

### Strategic Activities (Weekly)

- [ ] Review conversion metrics
- [ ] Optimize underperforming sequences
- [ ] Test new approaches
- [ ] Plan next week

---

**Remember:** Consistency beats intensity. 10 cold emails daily = 50/week = 200/month = 2,400/year.

At 5% reply rate and 30% close rate, that's 36 new clients per year.

Start small, stay consistent, scale what works.
