# Business Patterns Usage Guide

A comprehensive guide to all revenue-generating and business automation patterns in Fabric.

---

## Table of Contents

1. [Overview](#overview)
2. [Pattern Categories](#pattern-categories)
3. [Inbox Operations](#inbox-operations)
4. [Outreach Patterns](#outreach-patterns)
5. [Prospecting Patterns](#prospecting-patterns)
6. [Automation Patterns](#automation-patterns)
7. [Business Strategy Patterns](#business-strategy-patterns)
8. [Client Acquisition Patterns](#client-acquisition-patterns)
9. [Standalone Business Tools](#standalone-business-tools)
10. [Quick Reference Table](#quick-reference-table)

---

## Overview

These business patterns form a complete revenue generation and business automation toolkit. They're designed to work together in workflows that take you from prospecting to closed deals and ongoing client management.

**Target Users:**
- Solo founders and entrepreneurs
- Marketing and sales agencies
- Sales teams and SDRs
- Consultants and coaches
- Technical service providers
- Small-to-medium business owners

**Key Principle:** Each pattern produces structured, actionable output with ROI quantification and clear next steps.

---

## Pattern Categories

| Category | Purpose | Patterns |
|----------|---------|----------|
| Inbox Ops | Email triage and response | 3 patterns |
| Outreach | Cold email and follow-ups | 3 patterns |
| Prospecting | Lead discovery and analysis | 2 patterns |
| Automation | Workflow and system design | 3 patterns |
| Business Strategy | Financial and pricing | 2 patterns |
| Client Acquisition | Sales funnel and proposals | 5 patterns |
| Standalone | Website audits, AI agents | 5 patterns |

---

## Inbox Operations

### classify_email_reply

**Purpose:** Triage incoming email replies into actionable categories for sales routing.

**Usage:**
```bash
cat email.txt | fabric -p classify_email_reply
```

**Input:** Email content (from, subject, body, optional original outreach context)

**Output:** Classification report with:
- Category: INTERESTED / QUESTION / OBJECTION / NOT_INTERESTED / AUTO_REPLY / SPAM
- Confidence score (0-100%)
- Intent signals detected
- Recommended action with priority level

**Example:**
```bash
echo "Subject: Re: Your website audit
From: john@acmeplumbing.com

Thanks for reaching out. We've been thinking about updating our website.
What would something like this cost?" | fabric -p classify_email_reply
```

---

### flag_hot_lead

**Purpose:** Score and rank leads to identify which need immediate personal attention vs automated nurturing.

**Usage:**
```bash
cat lead_data.txt | fabric -p flag_hot_lead
```

**Input:** Email classification data + lead information (business, contact, timing, engagement signals)

**Output:** Lead scoring report with:
- Score (0-100) across 4 dimensions
- Tier: HOT (75-100) / WARM (50-74) / NURTURE (25-49) / LOW (0-24)
- Recommended response timing
- Approach strategy

**Scoring Breakdown:**
| Dimension | Max Points |
|-----------|------------|
| Intent signals | 40 |
| Engagement signals | 25 |
| Authority signals | 20 |
| Urgency signals | 15 |

**Response SLAs:**
- HOT: Respond within 1 hour
- WARM: Respond within 4 hours
- NURTURE: Respond within 24 hours
- LOW: Respond when convenient

---

### draft_reply

**Purpose:** Generate contextual, personalized email replies that handle objections and move toward meetings.

**Usage:**
```bash
cat email_context.txt | fabric -p draft_reply
```

**Input:** Original email + classification data + business context + objection type (if applicable)

**Output:**
- Complete reply draft with subject line
- Analysis of what's being addressed
- Alternative versions (shorter/longer)
- Objection handling scripts

**Objection Types Handled:**
| Type | Strategy |
|------|----------|
| Timing | Acknowledge, offer future touchpoint |
| Price | Reframe value, offer alternatives |
| Need | Explore deeper, quantify pain |
| Trust | Provide proof, offer trial |
| Authority | Offer materials for decision-maker |

**Framework Used:** LAER (Listen, Acknowledge, Explore, Respond)

---

## Outreach Patterns

### personalize_from_gaps

**Purpose:** Transform gap analysis into compelling personalized copy for cold outreach.

**Usage:**
```bash
cat gap_analysis.txt | fabric -p personalize_from_gaps
```

**Input:** Business gap description, business type, location, optional competitor/pain point context

**Output:** Personalization copy kit with 15+ snippets:
- Pain-focused angles (3 versions)
- Stat-based angles (3 versions)
- Local/contextual angles (3 versions)
- Question hooks (3 versions)
- Story/example hooks (3 versions)
- Subject line variations
- Channel-specific recommendations

**Guidelines:**
- 1-3 sentences max per snippet
- Specific > generic language
- Urgency through consequence, not hype

---

### draft_cold_email

**Purpose:** Write short, personalized cold emails (50-100 words) that get opened and replied to.

**Usage:**
```bash
cat prospect_info.txt | fabric -p draft_cold_email
```

**Input:**
- Business/owner name, industry, location, website
- Gap identified
- What you're selling
- Your name/company
- Optional proof points

**Output:**
- 5 subject line variations
- 3 email versions (recommended, alternate angle, shorter)
- Sending notes
- Follow-up email template

**Email Structure:**
1. Opening line about THEM (specific research)
2. Problem statement (1-2 sentences)
3. Solution tease with proof (1-2 sentences)
4. Clear CTA
5. P.S. line for skimmers

**Best Practices:**
- No pleasantries
- Lead with them, not you
- One idea per email
- Proof over promises

---

### draft_followup_sequence

**Purpose:** Create 3-5 email follow-up sequences that stay top-of-mind without annoying.

**Usage:**
```bash
cat original_email_context.txt | fabric -p draft_followup_sequence
```

**Input:** Original email context, business info, gap/pitch, status, proof points, likely objections

**Output:** Complete 5-email sequence over 14 days:

| Email | Day | Angle |
|-------|-----|-------|
| 1 | 0 | Initial outreach |
| 2 | 3 | Add value |
| 3 | 7 | Social proof |
| 4 | 10 | Different approach |
| 5 | 14 | Breakup email |

**Principles:**
- Never "just checking in"
- Add value each time
- Get shorter each email
- Different angle each touch
- Breakup email works

---

## Prospecting Patterns

### scrape_local_businesses

**Purpose:** Analyze search results to identify local businesses missing digital features.

**Usage:**
```bash
cat search_results.txt | fabric -p scrape_local_businesses
```

**Input Options:**
- Search criteria (vertical, location, feature gap, limit)
- Pasted search results or CSV data
- Business listing data

**Output:**
- Structured prospect list with tier classification
- Detailed business profiles
- Opportunity scores (1-10)
- Disqualified businesses with reasons
- Recommended next steps

**Priority Tiers:**
| Tier | Score | Priority |
|------|-------|----------|
| 1 | 8-10 | High - contact immediately |
| 2 | 5-7 | Medium - add to sequence |
| 3 | 1-4 | Lower - nurture list |

**Scoring Factors:**
- Review count (more = established)
- Rating (4+ = cares about reputation)
- Website quality (worse = more opportunity)
- Business size indicators

---

### analyze_business_gaps

**Purpose:** Identify specific, actionable gaps in a business's digital presence that represent sales opportunities.

**Usage:**
```bash
echo "Business: Acme Plumbing
Website: acmeplumbing.com
Industry: Plumbing
Location: Austin, TX" | fabric -p analyze_business_gaps
```

**Input:** Business info (name, location, industry, website URL or content), what you're selling, optional competitor/review context

**Output:**
- Overall gap score (0-10)
- Critical gaps (high revenue impact)
- Moderate gaps
- Competitive comparison
- Estimated revenue impact
- Pitch angles for each gap

**Gap Dimensions:**
| Dimension | What to Look For |
|-----------|------------------|
| Lead capture | Forms, chat, phone prominent? |
| Trust signals | Reviews, testimonials, certifications? |
| Local SEO | GMB, citations, local keywords? |
| Technical | Speed, mobile, SSL? |
| Content | Fresh, relevant, helpful? |
| Mobile | Responsive, thumb-friendly? |
| Competitive | How do competitors compare? |

**Revenue Impact Levels:**
- Critical: 20-50%+ conversion loss
- Major: 10-20% loss
- Minor: 5-10% loss
- Optimization: 5-15% improvement potential

---

## Automation Patterns

### automate_lead_enrichment

**Purpose:** Design automated systems that enrich lead data with company info, contacts, and behavioral signals.

**Usage:**
```bash
cat enrichment_requirements.txt | fabric -p automate_lead_enrichment
```

**Input:** Lead data source, CRM, enrichment needs, budget, volume, ICP criteria, sales workflow

**Output:**
- Complete automation workflow documentation
- Tool selection and comparison
- API integration steps
- Lead scoring model
- Error handling procedures
- CRM setup instructions
- Cost analysis
- Implementation roadmap

**Enrichment Steps:**
1. Data validation/cleaning
2. Company data (Clearbit/Apollo)
3. Email verification (Hunter.io)
4. Tech stack detection (BuiltWith)
5. LinkedIn profiles
6. Lead scoring (ICP fit)

**Tool Tiers:**
| Tier | Cost/Month | Tools |
|------|------------|-------|
| Free/Low | $0-50 | Hunter free tier, manual LinkedIn |
| Professional | $100-300 | Apollo, Clearbit, automated |
| Enterprise | $500+ | ZoomInfo, full automation |

**Cost Per Lead:** $0.12-0.15 with professional setup

---

### create_crm_workflow

**Purpose:** Design intelligent CRM automation workflows that save 10-20 hours/week per sales rep.

**Usage:**
```bash
cat crm_requirements.txt | fabric -p create_crm_workflow
```

**Input:** CRM platform, team structure, sales stages, pain points, lead sources, integration needs

**Output:**
- Lead routing rules
- Automated task workflows
- Email sequences (5-7 emails)
- Lead scoring automation
- Slack/email notifications
- Reporting dashboards
- Data hygiene workflows
- 6-week implementation roadmap

**Lead Routing Logic:**
| Source | Routing Rule |
|--------|--------------|
| Inbound | Round-robin |
| Outbound | Creator-owned |
| Enterprise | Senior AE |
| Territory | Geo-based |
| Industry | Specialist |

**Expected Impact:**
- 10-20 hours/week saved per rep
- <5 min lead response time
- 80% of follow-ups automated

---

### setup_customer_onboarding

**Purpose:** Design automated customer onboarding that reduces time-to-value by 40-60%.

**Usage:**
```bash
cat onboarding_requirements.txt | fabric -p setup_customer_onboarding
```

**Input:** Product type, customer segments, onboarding goals/"aha moment", pain points, complexity, team structure

**Output:**
- Complete onboarding journey map
- Phase-by-phase email sequences
- In-app automation triggers
- Milestone-based actions
- Customer health scoring
- At-risk intervention workflows
- Metrics dashboard
- Implementation roadmap

**Onboarding Phases:**
| Phase | Timeframe | Goal |
|-------|-----------|------|
| Welcome | Day 0 | Set expectations |
| Quick Wins | Days 1-7 | Reach "aha moment" |
| Activation | Days 8-30 | Feature adoption |
| Maturity | Days 31-90 | Advanced usage |
| Retention | Day 90+ | Expansion |

**Health Score Components:**
- Usage metrics (40%)
- Engagement metrics (30%)
- Outcome metrics (30%)

---

## Business Strategy Patterns

### build_financial_model

**Purpose:** Create investor-grade 3-year financial projections with monthly granularity.

**Usage:**
```bash
cat business_details.txt | fabric -p build_financial_model
```

**Input:** Business model, pricing, current state, revenue streams, cost structure, growth assumptions, funding status

**Output:**
- Executive summary
- Revenue model projections
- Cost structure breakdown
- Unit economics (CAC/LTV)
- 36-month P&L and cash flow
- Best/likely/worst scenarios
- Break-even analysis
- Sensitivity analysis
- Funding strategy
- Red flags/assumption validation

**Key Metrics Calculated:**
| Metric | Target |
|--------|--------|
| LTV:CAC ratio | 3:1+ |
| Gross margin (SaaS) | >70% |
| Monthly churn (SaaS) | <5% |
| Payback period | <12 months |

**Industry Benchmarks:**
- SaaS: 70%+ gross margin
- Agency: 20-30% gross margin
- Consulting: 40-60% gross margin

---

### optimize_pricing_strategy

**Purpose:** Design value-based pricing strategies that increase revenue by 20-50%.

**Usage:**
```bash
cat pricing_context.txt | fabric -p optimize_pricing_strategy
```

**Input:** Current offering, target customers, current pricing/performance, costs, competitors, value delivered

**Output:**
- Value analysis
- Competitive positioning
- Recommended pricing model
- Good/Better/Best tier structure
- Pricing psychology applications
- Annual vs monthly recommendations
- Discount guidelines
- Pricing page design
- A/B testing framework
- Financial impact projections

**Pricing Models:**
| Model | Best For |
|-------|----------|
| Flat rate | Simple products |
| Per-user | Team-based SaaS |
| Tiered | Multiple segments |
| Usage-based | Variable consumption |
| Value-based | High-impact outcomes |
| Freemium | Land-and-expand |

**Tier Distribution Target:**
- Entry: 20-30% of customers
- Mid (Most Popular): 60-70%
- Premium: 10-20%

---

## Client Acquisition Patterns

### create_outbound_sequence

**Purpose:** Create personalized B2B/B2C outbound sequences achieving >20% open rates and >5% response rates.

**Usage:**
```bash
cat prospect_details.txt | fabric -p create_outbound_sequence
```

**Input:** Target ICP, value proposition, top 3 pain points, social proof, desired CTA, sender info

**Output:**
- Complete 7-touch sequence (14-21 days)
- Email subject lines (3-5 variations)
- A/B message versions
- LinkedIn connection messages
- Cold call scripts (voicemail + live)
- A/B testing strategy
- Deliverability checklist
- CRM setup instructions

**Sequence Structure:**
| Touch | Day | Channel | Purpose |
|-------|-----|---------|---------|
| 1 | 0 | Email | Pattern interrupt + research |
| 2 | 3 | Email | Value/case study |
| 3 | 4 | LinkedIn | Connection request |
| 4 | 7 | Email | Educational content |
| 5 | 9 | Phone | Voicemail/conversation |
| 6 | 11 | Email | Different angle |
| 7 | 14 | Email | Breakup email |

---

### create_winning_proposal

**Purpose:** Create high-converting proposals (>40% close rate) for consulting, agency, and automation projects.

**Usage:**
```bash
cat project_details.txt | fabric -p create_winning_proposal
```

**Input:** Client info, project type, business problem, pain points, outcomes, budget, timeline, decision-makers

**Output:**
- Executive summary
- Situation analysis (current vs future state)
- Phased solution approach
- Value & ROI quantification
- Good/Better/Best pricing packages
- Timeline & milestones
- Case studies & social proof
- Risk mitigation & guarantees
- Clear next steps

**Pricing Tier Strategy:**
| Tier | Position | Multiplier |
|------|----------|------------|
| Essential | Entry point | 1x |
| Professional | Most Popular | 2-3x |
| Enterprise | Full service | 2-4x |

---

### qualify_leads

**Purpose:** Qualify leads using BANT, MEDDIC, CHAMP frameworks with 0-100 scoring.

**Usage:**
```bash
cat lead_info.txt | fabric -p qualify_leads
```

**Input:** Lead info (company/size/industry/revenue), contact details, source, engagement signals, timeline, budget signals

**Output:**
- Overall lead score (0-100)
- Qualification tier
- BANT analysis (each dimension 25pts)
- MEDDIC analysis (for enterprise)
- ICP fit score
- Buying intent score
- Red flags & risk assessment
- Recommended next actions

**Lead Scoring Formula:**
```
(ICP Fit Score × 0.4) + (Buying Intent Score × 0.6) = Total Score
```

**Tiers:**
| Tier | Score | Response Time |
|------|-------|---------------|
| Hot | 80-100 | 48 hours |
| Warm | 60-79 | 5-7 days |
| Cold | 40-59 | Nurture campaign |
| Disqualified | 0-39 | Archive |

---

### generate_lead_magnet

**Purpose:** Create high-converting lead magnets (>30% conversion rate) that attract qualified leads.

**Usage:**
```bash
cat audience_details.txt | fabric -p generate_lead_magnet
```

**Input:** Target audience, buyer journey stage, offering, competitors' lead magnets, expertise, resources

**Output:**
- 5-7 concept ideas with outlines
- Recommended lead magnet with full structure
- Landing page copy
- Email delivery sequence (5 emails)
- Promotion strategy
- Production checklist
- Success metrics
- Budget breakdown

**Format by Journey Stage:**
| Stage | Formats |
|-------|---------|
| Awareness | Ebooks, guides, checklists |
| Consideration | Case studies, templates, calculators |
| Decision | Free trials, demos, assessments |

**Expected Conversion:** 20-40% landing page rate

---

### build_sales_funnel

**Purpose:** Design multi-stage sales funnels (TOFU/MOFU/BOFU) with conversion optimization.

**Usage:**
```bash
cat funnel_requirements.txt | fabric -p build_sales_funnel
```

**Input:** Business model, target audience, product/pricing, revenue goals, channels, conversion data, sales cycle

**Output:**
- TOFU design (traffic, content, lead magnets)
- MOFU design (nurture, engagement, qualification)
- BOFU design (conversion, decision support)
- Content mapping by stage
- Conversion paths & user flows
- Funnel metrics & KPIs
- A/B testing roadmap
- Retargeting strategies
- 6-month implementation roadmap

**Benchmark Conversion Rates:**
| Stage | Metric | Target |
|-------|--------|--------|
| TOFU | Visitor-to-Lead | 2-5% |
| MOFU | Lead-to-MQL | 20-40% |
| MOFU | MQL-to-SQL | 30-50% |
| BOFU | SQL-to-Trial | 30-50% |
| BOFU | Trial-to-Paid | 15-30% |

---

## Standalone Business Tools

### audit_business_website

**Purpose:** Identify revenue leaks, conversion killers, and competitive disadvantages with quantified impact.

**Usage:**
```bash
echo "https://example.com" | fabric -p audit_business_website
# OR
cat website_html.txt | fabric -p audit_business_website
```

**Input:** Website URL or content, business context (type/customer/location)

**Output:**
- Overall score (0-10)
- 8-dimension scorecard
- Critical pain points with revenue impact
- Major improvement opportunities
- Competitive gaps
- Revenue impact analysis
- Prioritized action plan
- Quick wins checklist

**Scoring Dimensions:**
1. First impression & clarity
2. Trust & credibility
3. Conversion architecture
4. Mobile experience
5. Local SEO readiness
6. Content quality
7. Technical foundation
8. Competitive positioning

**Special Case:** "No website" = CRITICAL BUSINESS EMERGENCY with 7-day MVP plan

---

### automate_business_plan

**Purpose:** Convert high-level business plans into executable automated workflows and code.

**Usage:**
```bash
cat business_plan.txt | fabric -p automate_business_plan
```

**Input:** Business plan summary with operational pillars, pain points, automation priorities, tech stack

**Output:**
- Phase 1: Project architecture/folder structure
- Phase 2: Digital Workers/agents needed
- Phase 3: Starter code blocks (Python/Bash)
- Phase 4: Implementation checklist

**Examples of Generated Code:**
- Cold emailing → Python SMTP script
- Content marketing → Fabric pattern chains
- Lead management → CRM integration scripts

---

### automate_task

**Purpose:** Take any repetitive task and write a safe, efficient automation script.

**Usage:**
```bash
echo "Organize my Downloads folder by file type" | fabric -p automate_task
```

**Input:** Task description (goal, inputs, outputs), environment (OS, tools, APIs), schedule

**Output:**
- Prerequisites list
- Complete executable script
- Shebang and dependencies
- Modular commented code
- Error handling
- "How to Run" example

**Tool Selection:**
- Bash: File system, OS tasks
- Python: Logic, APIs, text processing

---

### create_lead_guardian

**Purpose:** Design custom AI agent for local businesses to ensure no potential customer is ignored.

**Usage:**
```bash
cat business_details.txt | fabric -p create_lead_guardian
```

**Input:** Business type/name/location, service hours, services, customer scenarios, booking goals, lead sources

**Output:**
- Section 1: Agent Strategy (persona, goals)
- Section 2: System Prompt (ready to use)
- Section 3: Implementation Guide (tech stack)

**Platforms:**
- SMS: Twilio, HighLevel
- Chat: Website embed, Intercom
- Voice: Vapi.ai

**Use Cases:**
- 24/7 emergency services (plumbing, HVAC)
- Medical/dental practice intake
- Law firm consultations
- Local service lead capture

---

### create_monetization_plan

**Purpose:** Help technical founders turn assets (APIs, servers, Fabric patterns) into profitable revenue streams.

**Usage:**
```bash
cat technical_assets.txt | fabric -p create_monetization_plan
```

**Input:** Business structure, technical infrastructure, current services, skills, target market, goals

**Output:**
- Section 1: Business Structure (leveraging assets)
- Section 2: Offer Map (Free Audit → Paid Setup → Monthly Retainer)
- Section 3: Technical Execution (Pattern-as-a-Service)
- Section 4: First Client Sprint (5-day plan)
- Section 5: Financial Projections (margins)

**Business Model Options:**
| Model | Description |
|-------|-------------|
| SaaS | Selling access to tool |
| Service/Agency | Selling results |
| Productized Service | Results at scale |

---

## Quick Reference Table

| Pattern | Category | Primary Use | Output Type |
|---------|----------|-------------|-------------|
| classify_email_reply | Inbox Ops | Triage emails | Classification + action |
| flag_hot_lead | Inbox Ops | Prioritize leads | Score + tier |
| draft_reply | Inbox Ops | Write responses | Email draft |
| personalize_from_gaps | Outreach | Create copy | Copy snippets |
| draft_cold_email | Outreach | Write cold emails | Email package |
| draft_followup_sequence | Outreach | Follow-up emails | 5-email sequence |
| scrape_local_businesses | Prospecting | Find prospects | Prospect list |
| analyze_business_gaps | Prospecting | Identify opportunities | Gap analysis |
| automate_lead_enrichment | Automation | Design enrichment | Workflow doc |
| create_crm_workflow | Automation | Design CRM flows | Automation plan |
| setup_customer_onboarding | Automation | Design onboarding | Journey map |
| build_financial_model | Strategy | Financial planning | 3-year projections |
| optimize_pricing_strategy | Strategy | Pricing design | Pricing strategy |
| create_outbound_sequence | Acquisition | Multi-channel outreach | 7-touch sequence |
| create_winning_proposal | Acquisition | Close deals | Proposal doc |
| qualify_leads | Acquisition | Score leads | Qualification report |
| generate_lead_magnet | Acquisition | Attract leads | Lead magnet plan |
| build_sales_funnel | Acquisition | Design funnels | Funnel design |
| audit_business_website | Standalone | Website analysis | Audit report |
| automate_business_plan | Standalone | Plan to execution | Code + workflows |
| automate_task | Standalone | Script any task | Executable script |
| create_lead_guardian | Standalone | AI agent design | Agent config |
| create_monetization_plan | Standalone | Revenue strategy | Monetization roadmap |

---

## Next Steps

1. **Start with Prospecting:** Use `scrape_local_businesses` → `analyze_business_gaps`
2. **Build Outreach:** Use `personalize_from_gaps` → `draft_cold_email`
3. **Handle Responses:** Use `classify_email_reply` → `flag_hot_lead` → `draft_reply`
4. **Close Deals:** Use `qualify_leads` → `create_winning_proposal`
5. **Scale Operations:** Use automation patterns to systematize

See [BUSINESS_OPERATIONS_DAILY_GUIDE.md](./BUSINESS_OPERATIONS_DAILY_GUIDE.md) for daily workflow recommendations.

See [PATTERN_CHAINING_EXAMPLES.md](./PATTERN_CHAINING_EXAMPLES.md) for complex workflow examples.
