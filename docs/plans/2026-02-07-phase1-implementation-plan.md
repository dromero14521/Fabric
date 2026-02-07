# Phase 1 Implementation Plan: Revenue Generation Patterns

**Date:** 2026-02-07
**Goal:** Get leads flowing and book calls within 2 weeks
**Patterns:** 6 core patterns for prospecting and initial outreach

---

## Overview

Phase 1 focuses on the minimum viable prospecting workflow:

```
scrape_local_businesses → analyze_business_gaps → draft_cold_email
                                                         ↓
                         flag_hot_lead ← classify_email_reply
                                                         ↓
                                              personalize_from_gaps
```

---

## Pattern 1: `prospecting/scrape_local_businesses`

**Priority:** 1 (Start here)
**Effort:** 2-3 hours
**Dependencies:** None

### What It Does
Takes a vertical + location + feature gap and outputs structured business data.

### Input Example
```
Vertical: plumbers
Location: Seattle, WA
Feature Gap: no online booking
Limit: 50 businesses
```

### Output Example
```markdown
| Business Name | Phone | Website | Google Rating | Reviews | Has Online Booking |
|---------------|-------|---------|---------------|---------|-------------------|
| ABC Plumbing | 206-555-1234 | abcplumbing.com | 4.5 | 127 | No |
```

### Implementation Notes
- Output as structured markdown table or JSON
- Include fields needed for personalization
- Flag obvious disqualifiers (closed, bad reviews)

---

## Pattern 2: `prospecting/analyze_business_gaps`

**Priority:** 2
**Effort:** 2-3 hours
**Dependencies:** Works standalone or after scrape

### What It Does
Analyzes a business website/listing and identifies missing features.

### Input Example
```
Business: ABC Plumbing
Website: https://abcplumbing.com
Google Listing: [paste or describe]
```

### Output Example
```markdown
## Gap Analysis: ABC Plumbing

**Overall Gap Score: 7/10** (High opportunity)

### Critical Gaps (Revenue Impact)
- ❌ No online booking - losing after-hours leads
- ❌ No click-to-call on mobile - friction for urgent calls
- ❌ No chatbot/live chat - no 24/7 lead capture

### Moderate Gaps
- ⚠️ No customer reviews displayed on site
- ⚠️ Generic stock photos (low trust)
- ⚠️ No service area page (SEO issue)

### Minor Gaps
- 💡 No SSL certificate
- 💡 Slow page load (3.2s)

### Recommended Pitch Angle
Lead with: "You're losing after-hours leads because customers can't book online at 10pm"
```

### Implementation Notes
- Score gaps by revenue impact
- Generate specific pitch angle for outreach
- Keep analysis actionable, not exhaustive

---

## Pattern 3: `outreach/personalize_from_gaps`

**Priority:** 3
**Effort:** 1-2 hours
**Dependencies:** Best after analyze_business_gaps

### What It Does
Converts gap analysis into compelling copy snippets for emails.

### Input Example
```
Gap: No online booking
Business Type: Plumber
Location: Seattle
```

### Output Example
```markdown
## Personalization Snippets

### Pain Point Hook
"When a pipe bursts at 10pm, your customers can't book online - they call whoever shows up first on Google."

### Stat-Based Hook
"63% of service bookings happen outside business hours. Without online booking, you're invisible to them."

### Local Hook
"Seattle homeowners expect to book everything online - from dinner reservations to plumber visits."

### Question Hook
"How many calls did you miss last weekend while you were on a job?"

### Testimonial-Style Hook
"One of my plumber clients added online booking and got 12 new jobs in the first month - all from after-hours requests."
```

### Implementation Notes
- Generate 3-5 variations per gap
- Include different angles (pain, stats, local, question)
- Keep each snippet under 2 sentences

---

## Pattern 4: `outreach/draft_cold_email`

**Priority:** 4
**Effort:** 2-3 hours
**Dependencies:** Best with gap analysis + personalization

### What It Does
Creates a complete cold email from lead data and gaps.

### Input Example
```
Business: ABC Plumbing
Owner: Mike Johnson (if known)
Gap: No online booking
Location: Seattle
Your Service: AI-powered booking and lead capture chatbot
```

### Output Example
```markdown
**Subject Line Options:**
1. Quick question about ABC Plumbing's website
2. Noticed something about your online booking
3. How Seattle plumbers are getting more jobs

---

**Email:**

Hi Mike,

I was looking for a plumber in Seattle and found ABC Plumbing - great reviews on Google.

I noticed you don't have online booking on your site. That means when someone's pipe bursts at 10pm, they can't schedule with you - they'll call whoever shows up first.

I help plumbers add 24/7 booking and lead capture. One of my clients got 12 new jobs in the first month just from after-hours requests.

Worth a quick call to see if this fits your business?

[Your Name]

P.S. I can show you exactly how it works in 10 minutes - no pitch, just a demo.

---

**Sending Notes:**
- Best send time: Tuesday-Thursday, 7-8am (before they're on jobs)
- Follow up if no reply in 3 days
```

### Implementation Notes
- Keep under 100 words
- One clear CTA (call or reply)
- P.S. line for skimmers
- Include subject line variations

---

## Pattern 5: `inbox_ops/classify_email_reply`

**Priority:** 5
**Effort:** 1-2 hours
**Dependencies:** None (works on any email)

### What It Does
Classifies incoming email replies for routing.

### Input Example
```
From: mike@abcplumbing.com
Subject: Re: Quick question about ABC Plumbing's website

Yeah I've been thinking about this. What does it cost? We're pretty busy right now but maybe in a few weeks.
```

### Output Example
```markdown
## Classification: INTERESTED

**Confidence:** 85%

**Signals Detected:**
- ✅ Acknowledges problem ("been thinking about this")
- ✅ Asks about pricing (buying signal)
- ⚠️ Timeline objection ("in a few weeks")

**Intent:** Pricing inquiry + soft timeline objection

**Recommended Action:** WARM - Respond today with pricing range, address timeline softly

**Suggested Response Approach:**
- Provide pricing range (don't quote exact)
- Acknowledge they're busy (validate)
- Offer to set up for "when you're ready"
- Keep door open
```

### Implementation Notes
- Categories: INTERESTED, QUESTION, OBJECTION, NOT_INTERESTED, AUTO_REPLY, SPAM
- Include confidence score
- Extract key signals for response

---

## Pattern 6: `inbox_ops/flag_hot_lead`

**Priority:** 6
**Effort:** 1-2 hours
**Dependencies:** Best after classify_email_reply

### What It Does
Scores reply urgency for prioritization.

### Input Example
```
Classification: INTERESTED
Reply Content: "Yeah let's talk. Can you call me today? 206-555-1234"
Original Outreach Date: 2026-02-05
Reply Date: 2026-02-07
```

### Output Example
```markdown
## Lead Score: HOT 🔥

**Priority:** Contact within 1 hour
**Score:** 95/100

**Hot Signals:**
- ✅ Asks for call (high intent)
- ✅ Provides phone number (friction removed)
- ✅ "Today" = urgency
- ✅ Replied within 48 hours (engaged)

**Contact Info:**
- Phone: 206-555-1234
- Best time: Now (they asked for today)

**Talking Points:**
1. Thank them for quick reply
2. Reference their specific gap (online booking)
3. Offer 15-min demo, not a sales call
4. Ask about their current booking process

**One-Click Actions:**
- [ ] Call now
- [ ] Send calendar link
- [ ] Mark contacted
```

### Implementation Notes
- Three tiers: HOT (1 hour), WARM (today), NURTURE (sequence)
- Score 0-100 for ranking multiple leads
- Include specific talking points from context

---

## Implementation Order

```
Day 1-2: scrape_local_businesses + analyze_business_gaps
Day 3:   personalize_from_gaps + draft_cold_email
Day 4:   classify_email_reply + flag_hot_lead
Day 5:   Test full workflow end-to-end
```

---

## Testing the Workflow

After all 6 patterns are built, test with real scenario:

1. **Input:** "Find plumbers in Seattle without online booking"
2. **Run:** scrape → analyze → personalize → draft
3. **Output:** 10 ready-to-send cold emails
4. **Send:** Manually send 10 emails
5. **Wait:** Monitor for replies
6. **Process:** classify → flag → respond to hot leads

**Success Metric:** 1+ booked call from first 10 emails

---

## File Structure After Phase 1

```
data/patterns/
├── prospecting/
│   ├── scrape_local_businesses/
│   │   ├── system.md
│   │   └── user.md
│   └── analyze_business_gaps/
│       ├── system.md
│       └── user.md
├── outreach/
│   ├── personalize_from_gaps/
│   │   ├── system.md
│   │   └── user.md
│   └── draft_cold_email/
│       ├── system.md
│       └── user.md
└── inbox_ops/
    ├── classify_email_reply/
    │   ├── system.md
    │   └── user.md
    └── flag_hot_lead/
        ├── system.md
        └── user.md
```

---

## Next Steps After Phase 1

1. **Phase 2:** Add follow-up sequences and reply drafting
2. **Phase 3:** Add remaining prospecting patterns (enrich, score)
3. **Iterate:** Refine patterns based on what's working
