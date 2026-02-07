# Example Inputs for personalize_from_gaps

Use one of the following input formats to generate personalized copy snippets:

---

## Example 1: Simple Gap Input

```
Gap: No online booking
Business Type: Plumber
Location: Seattle, WA
```

---

## Example 2: Detailed Gap from Analysis

```
Gap Analysis Output:

Business: ABC Plumbing
Gap: No online booking capability

Revenue Impact: HIGH
- Losing after-hours leads (40% of searches happen outside business hours)
- Customers choosing competitors with instant booking
- Missed emergency calls when on other jobs

Customer Frustration:
- "I needed a plumber at 10pm and couldn't book anyone"
- "I called 3 plumbers, went with the one who answered"

Competitor Context:
- 2 of 5 top local competitors have online booking
- Top competitor (RapidPlumb) gets 4.9 stars, mentions "easy booking" in reviews
```

---

## Example 3: Multiple Gaps

```
Business: Sunshine Dental
Location: Tampa, FL
Industry: Dental Practice

Gap 1: No online appointment booking
Gap 2: No patient reviews displayed on website
Gap 3: No virtual consultation option

Generate personalization hooks for each gap.
```

---

## Example 4: Specific Service Context

```
Gap: No live chat or chatbot
Business Type: Personal Injury Law Firm
Location: Chicago, IL

Context:
- Potential clients are often in crisis/urgent situations
- They may be researching late at night after an accident
- Competitor firms have 24/7 intake
- Average case value: $15,000-50,000

My Service: AI-powered intake chatbot that qualifies leads 24/7
```

---

## Example 5: Local Market Context

```
Gap: No mobile-friendly website
Business Type: HVAC Contractor
Location: Phoenix, AZ

Local Context:
- Phoenix summers hit 110°F+ regularly
- AC emergencies are true emergencies (health risk)
- 70% of "AC repair near me" searches are mobile
- Peak season is April-September

Competitor Context:
- Top 3 competitors all have mobile-responsive sites
- One competitor specifically mentions "Book from your phone"
```

---

## Example 6: Gap from Prospect List

```
From scrape_local_businesses output:

Business: Elite Auto Repair
Rating: 4.6 (234 reviews)
Gap Confirmed: No online scheduling
Location: Denver, CO

Review Mentions:
- "Hard to get through on the phone" (appears 3 times)
- "Wish they had online booking" (appears 2 times)

Generate hooks that reference their own customer feedback.
```

---

## Example 7: B2B/Professional Services

```
Gap: No client portal or document sharing
Business Type: Accounting Firm
Location: Austin, TX
Target Clients: Small businesses, 5-50 employees

Context:
- Tax season creates document chaos
- Clients email sensitive docs insecurely
- Competitors using Sharefile, secure portals
- Firm has 150+ clients, 2 CPAs

Pain Points:
- Chasing clients for documents
- Version control nightmares
- Compliance/security concerns
```

---

## Example 8: E-commerce/Retail Gap

```
Gap: No abandoned cart recovery
Business Type: Online boutique clothing store
Location: Based in Nashville, ships nationwide

Context:
- Average cart value: $85
- Estimated abandonment rate: 70% (industry average)
- Monthly traffic: ~5,000 visitors
- Current email list: 800 subscribers

My Service: Automated abandoned cart email sequence
```

---

## Quick Input Template

```
Gap: [What's missing]
Business Type: [Industry]
Location: [City, State]

Context (optional):
- [Relevant industry context]
- [Competitor information]
- [Customer pain points]
- [Seasonal/timing factors]

My Service: [What I'm selling to fix this gap]

Specific Angles to Emphasize:
- [Angle 1]
- [Angle 2]
```
