# AI Agency & SaaS Startup Patterns Design

**Date:** 2026-02-07
**Status:** Approved
**Author:** Collaborative design session

## Overview

A comprehensive pattern library for AI agencies and SaaS startups, organized around actual business workflows. Designed for a hybrid business model: AI consulting agency + productized SaaS for local business prospecting and outreach automation.

### Business Context

- **Model:** AI Agency deploying as SaaS + consulting for small businesses
- **Core Product:** Local business prospecting and outreach automation
  1. Scrape Google for local businesses missing features
  2. Draft personalized outreach emails with enriched data
  3. Monitor inbox for replies, flag hot leads for personal follow-up
- **Constraint:** Funding pressure - patterns must ship faster or generate revenue faster

### Design Principles

- **Workflow-Centric:** Organized by how work flows through the business
- **Revenue-First Priority:** Prospecting and outreach patterns ship first
- **Composable:** Patterns can chain together into complete workflows
- **Practical:** Each pattern solves a specific, recurring problem

---

## Pattern Library Structure

**Total: 38 patterns across 6 workflow categories**

```
data/patterns/
├── prospecting/           (5 patterns)  - Find and qualify leads
├── outreach/              (6 patterns)  - Contact and nurture leads
├── inbox_ops/             (6 patterns)  - Monitor, triage, respond
├── client_delivery/       (8 patterns)  - Fulfill client work
├── product_dev/           (9 patterns)  - Ship your SaaS
└── internal_ops/          (10 patterns) - Run your business
```

---

## Category 1: Prospecting (5 patterns)

Find local businesses missing features you offer, enrich their data, and score for outreach.

### `prospecting/scrape_local_businesses`

**Purpose:** Find businesses on Google missing your features
**Input:** Vertical + location + feature gap (e.g., "plumbers in Seattle without online booking")
**Output:** Structured business data: name, address, phone, website, Google rating, review count

### `prospecting/analyze_business_gaps`

**Purpose:** Identify what's missing from a business's digital presence
**Input:** Business website URL or Google listing
**Output:** Gap score + list of opportunities (no chatbot, no click-to-call, slow site, no SSL, missing Google Business features)

### `prospecting/enrich_lead_data`

**Purpose:** Pull additional info for personalization
**Input:** Basic business info (name, website, location)
**Output:** Owner name (if findable), social profiles, tech stack detection, recent reviews sentiment, competitor comparison

### `prospecting/score_lead_quality`

**Purpose:** Rank leads by fit, urgency, and revenue potential
**Input:** Enriched lead data
**Output:** ICP fit (1-10), urgency signals, estimated deal size, ease of contact, priority tier (Hot/Warm/Cold)

### `prospecting/build_prospect_list`

**Purpose:** Orchestrator pattern that chains the above into a complete prospecting workflow
**Input:** Target criteria (vertical, location, gaps to find)
**Output:** Complete prospect list with all enriched data, scored and ranked

---

## Category 2: Outreach (6 patterns)

Contact prospects with personalized messaging based on their specific gaps.

### `outreach/draft_cold_email`

**Purpose:** Personalized first-touch email
**Input:** Enriched lead data + gap analysis
**Output:** Cold email leading with their specific problem, short, direct, one clear CTA

**Example opener:** "I noticed your site doesn't have online booking - you're losing customers who want to schedule at 10pm"

### `outreach/draft_followup_sequence`

**Purpose:** Multi-touch follow-up emails (3-5 emails over 2 weeks)
**Input:** Initial email context + lead data
**Output:** Follow-up sequence, each adding new value: case study, quick tip, social proof, breakup email

### `outreach/personalize_from_gaps`

**Purpose:** Convert gap analysis into compelling copy snippets
**Input:** Gap analysis output
**Output:** Pain-point copy (e.g., "No chatbot" → "You're missing leads while you're on jobs")

### `outreach/generate_subject_lines`

**Purpose:** A/B test subject line variations
**Input:** Email body
**Output:** 5 subject line variations: curiosity, direct, question, local reference, urgency. Ranked by predicted open rate.

### `outreach/create_video_script`

**Purpose:** Personalized Loom/video outreach script for high-value prospects
**Input:** Lead data + gap analysis
**Output:** 60-second script: quick intro, show their website, point out gap, offer help

### `outreach/localize_outreach`

**Purpose:** Adjust messaging for regional tone
**Input:** Email draft + target location
**Output:** Regionally-adjusted messaging with local references (Seattle vs. Texas vs. Miami communicate differently)

---

## Category 3: Inbox Operations (6 patterns)

Monitor incoming replies, classify intent, and route hot leads for personal follow-up.

### `inbox_ops/classify_email_reply`

**Purpose:** Categorize incoming email replies
**Input:** Email content
**Output:** Classification: INTERESTED, QUESTION, OBJECTION, NOT_INTERESTED, AUTO_REPLY, SPAM

### `inbox_ops/extract_reply_intent`

**Purpose:** Deep analysis of what they want
**Input:** Email reply + original context
**Output:** What they're asking, their timeline, objections mentioned, preferred contact method, decision-maker signals

### `inbox_ops/flag_hot_lead`

**Purpose:** Score replies for urgency
**Input:** Classified email + intent extraction
**Output:** Priority level: HOT (contact within 1 hour), WARM (contact today), NURTURE (keep in sequence)

**Hot signals:** Asks about pricing, mentions timeline, asks for call, replies quickly

### `inbox_ops/draft_reply`

**Purpose:** Generate contextual response
**Input:** Their email + original context + your voice/tone guidelines
**Output:** Reply that answers their question, handles objection if present, moves toward booking a call

### `inbox_ops/summarize_thread`

**Purpose:** Condense long email threads for quick review
**Input:** Full email thread
**Output:** Who they are, what they want, where we are in conversation, recommended next action

### `inbox_ops/escalate_to_human`

**Purpose:** Format hot lead for personal queue
**Input:** Hot lead thread + all context
**Output:** One-paragraph summary, their question, recommended response, link to thread, one-click reply option

---

## Category 4: Client Delivery (8 patterns)

Onboard clients, deliver projects, manage scope, and maximize retention.

### `client_delivery/create_onboarding_checklist`

**Purpose:** Define what you need from client to start
**Input:** Service type
**Output:** Checklist: API keys, login credentials, brand assets, stakeholder contacts, analytics access

### `client_delivery/kickoff_agenda`

**Purpose:** Structure the kickoff call
**Input:** Project type + client info
**Output:** 30-minute agenda: intros, confirm scope, success metrics, communication cadence, decision-maker, next steps

### `client_delivery/scope_project`

**Purpose:** Define deliverables, timeline, boundaries
**Input:** Client conversation/notes
**Output:** Deliverables list, what's NOT included, timeline with milestones, approval process, change request policy

### `client_delivery/draft_status_update`

**Purpose:** Weekly client update email
**Input:** Project progress notes
**Output:** What was done, what's next, any blockers, action items for client. Professional and brief.

### `client_delivery/document_deliverable`

**Purpose:** Package what you built for handoff
**Input:** Completed work + project context
**Output:** Deliverable documentation: what was built, how to use it, credentials, maintenance notes

### `client_delivery/handle_scope_creep`

**Purpose:** Respond to "can you also..." requests
**Input:** Scope creep request + original scope
**Output:** Response: acknowledge, explain outside scope, offer as add-on with price, or suggest phase 2

### `client_delivery/create_qbr_report`

**Purpose:** Quarterly business review for retainer clients
**Input:** Client metrics + work performed
**Output:** Results achieved, ROI metrics, recommendations for next quarter, expansion opportunities

### `client_delivery/request_testimonial`

**Purpose:** Ask for review/case study at right moment
**Input:** Completed project + results achieved
**Output:** Personalized ask based on results, makes it easy to say yes

---

## Category 5: Product Development (9 patterns)

Ship your SaaS faster with consistent development workflows.

### `product_dev/write_feature_spec`

**Purpose:** Turn idea into buildable spec
**Input:** Rough feature idea
**Output:** Problem statement, proposed solution, user flow, edge cases, out of scope, technical considerations

### `product_dev/create_user_story`

**Purpose:** Agile-style stories with acceptance criteria
**Input:** Feature description
**Output:** "As a [user], I want [action], so that [outcome]" + acceptance criteria, definition of done, story points

### `product_dev/design_api_endpoint`

**Purpose:** Define API contract before coding
**Input:** Endpoint requirements
**Output:** Endpoint path, method, request schema, response schema, error codes, auth requirements, rate limits

### `product_dev/generate_test_cases`

**Purpose:** Test scenarios from spec
**Input:** Feature spec
**Output:** Happy path tests, edge cases, error scenarios, integration test needs

### `product_dev/review_pull_request`

**Purpose:** Code review checklist and feedback
**Input:** Code diff
**Output:** Security concerns, performance issues, code style, missing tests, complexity warnings, approval recommendation

### `product_dev/write_changelog_entry`

**Purpose:** User-facing release notes
**Input:** Changes shipped
**Output:** Clear, user-friendly description of what changed and why it matters

### `product_dev/debug_error`

**Purpose:** Systematic error diagnosis
**Input:** Error message/logs
**Output:** Likely causes ranked by probability, diagnostic steps, fix suggestions

### `product_dev/create_deployment_checklist`

**Purpose:** Pre-deploy verification steps
**Input:** Deployment type + environment
**Output:** Checklist: tests passing, migrations ready, rollback plan, monitoring alerts, notification plan

### `product_dev/prioritize_backlog`

**Purpose:** Stack rank features by impact vs effort
**Input:** Feature list
**Output:** Ranked list with scores: revenue impact, user demand, effort estimate, risk level, justification

**Critical pattern for funding-constrained situations.**

---

## Category 6: Internal Operations (10 patterns)

Run your business efficiently with repeatable processes.

### `internal_ops/write_sop`

**Purpose:** Standard operating procedure from process description
**Input:** Rough process description
**Output:** Step-by-step procedure, tools needed, common mistakes, troubleshooting, owner, review frequency

### `internal_ops/create_meeting_agenda`

**Purpose:** Structure any meeting type
**Input:** Meeting type + context
**Output:** Timed agenda with objectives, discussion points, decisions needed, action items section

### `internal_ops/summarize_meeting`

**Purpose:** Action items and decisions from transcript
**Input:** Meeting transcript/notes
**Output:** Attendees, decisions made, action items with owners and deadlines, open questions, follow-up needed?

### `internal_ops/draft_invoice`

**Purpose:** Generate invoice from project/time data
**Input:** Project details or time entries
**Output:** Line items, amounts, payment terms, professional formatting

### `internal_ops/track_time_entry`

**Purpose:** Categorize work for billing/analysis
**Input:** Work description
**Output:** Client/project, category, billable/non-billable, time estimate

### `internal_ops/weekly_review`

**Purpose:** Personal productivity review
**Input:** Week's activities
**Output:** What got done, what didn't, blockers, energy levels, priorities for next week

### `internal_ops/generate_financial_report`

**Purpose:** Revenue, expenses, runway, projections
**Input:** Raw financial numbers
**Output:** Revenue this month, MRR trend, expenses breakdown, burn rate, runway remaining, cash flow projection

**Critical pattern for funding pressure situations.**

### `internal_ops/document_decision`

**Purpose:** Record why you made a choice (ADR-style)
**Input:** Decision made
**Output:** What was decided, options considered, why this choice, who decided, revisit date

### `internal_ops/onboard_contractor`

**Purpose:** Checklist and context for new team member
**Input:** Role description
**Output:** Access needed, tools to set up, key docs to read, first week tasks, who to ask for what

### `internal_ops/create_dashboard_metrics`

**Purpose:** Define KPIs for business health
**Input:** Business area
**Output:** Metric name, calculation, data source, target, review frequency, owner

---

## Implementation Priority

Given funding constraints, implement in this order:

### Phase 1: Revenue Generation (Week 1-2)
1. `prospecting/scrape_local_businesses`
2. `prospecting/analyze_business_gaps`
3. `outreach/draft_cold_email`
4. `outreach/personalize_from_gaps`
5. `inbox_ops/classify_email_reply`
6. `inbox_ops/flag_hot_lead`

**Goal:** Start generating leads and booking calls immediately.

### Phase 2: Efficiency (Week 3-4)
7. `outreach/draft_followup_sequence`
8. `inbox_ops/draft_reply`
9. `product_dev/prioritize_backlog`
10. `internal_ops/generate_financial_report`

**Goal:** Automate follow-up, understand runway.

### Phase 3: Scale (Week 5-8)
11. Remaining prospecting patterns
12. Remaining outreach patterns
13. Client delivery patterns
14. Product dev patterns

**Goal:** Handle more volume, deliver better.

### Phase 4: Optimization (Ongoing)
15. Internal ops patterns
16. Refinement of all patterns based on usage

---

## Technical Notes

### Pattern Structure
Each pattern follows Fabric standard structure:
```
pattern_name/
├── system.md    # Identity, steps, output instructions
└── user.md      # Example inputs
```

### Integration Points
- **Email:** Patterns designed to work with SMTP, Gmail API, or email automation tools
- **Scraping:** Patterns output structured data for downstream processing
- **CRM:** Outputs compatible with HubSpot, Pipedrive, or simple JSON/CSV

### Chaining Patterns
Patterns are designed to chain:
```
scrape_local_businesses
  → analyze_business_gaps
    → enrich_lead_data
      → score_lead_quality
        → draft_cold_email
```

---

## Success Metrics

After implementation, measure:

- **Prospecting:** Leads generated per hour of effort
- **Outreach:** Reply rate, positive reply rate
- **Inbox Ops:** Time to respond to hot leads
- **Client Delivery:** Project delivery time, scope creep incidents
- **Product Dev:** Features shipped per week
- **Internal Ops:** Hours saved on admin tasks

---

## Next Steps

1. ✅ Design approved
2. ⬜ Create implementation plan
3. ⬜ Build Phase 1 patterns (revenue generation)
4. ⬜ Test with real prospecting workflow
5. ⬜ Iterate based on results
