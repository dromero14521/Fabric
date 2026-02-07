# Example Inputs for flag_hot_lead

Use one of the following input formats to score and prioritize a lead:

---

## Example 1: Obvious Hot Lead

```
Email Classification: INTERESTED
Confidence: 95%

From: david@davidjohnsonlaw.com
Subject: Re: Your email about intake
Received: Today at 10:15 AM

Reply Content:
"Yes let's talk. Can you call me today? My direct line is 312-555-9999. I'm free after 2pm.

David Johnson"

Original Outreach Date: Yesterday
Business: Johnson & Associates Law Firm
Industry: Personal Injury Law
Location: Chicago, IL
Gap: No 24/7 intake system
```

---

## Example 2: Warm Lead with Questions

```
Email Classification: INTERESTED
Confidence: 85%

From: marcus@eliteautorepair.com
Subject: Re: Online booking system
Received: Today at 8:30 AM

Reply Content:
"A few questions:

1. What's the monthly cost?
2. Does it integrate with our current software (we use Shop-Ware)?
3. How long does setup take?
4. Can customers book specific services or just general appointments?

I've been meaning to add online booking for a while. If the price is right and it works with our system, I'm interested.

Marcus
Owner, Elite Auto Repair"

Original Outreach Date: 2 days ago
Business: Elite Auto Repair
Industry: Auto Repair
Location: Denver, CO
Gap: No online scheduling
Rating: 4.6 (234 reviews)
```

---

## Example 3: Interested but Timing Objection

```
Email Classification: OBJECTION
Confidence: 80%

From: mike@abcplumbing.com
Subject: Re: Quick question about ABC Plumbing's website
Received: This morning

Reply Content:
"Yeah I've been thinking about this. What does it cost? We're pretty slammed right now but maybe in a few weeks."

Original Outreach Date: 3 days ago
Business: ABC Plumbing
Industry: Plumbing
Location: Seattle, WA
Gap: No online booking
```

---

## Example 4: Authority Referral

```
Email Classification: QUESTION
Confidence: 70%

From: jennifer@eliteautorepair.com
Subject: RE: Online scheduling
Received: Yesterday

Reply Content:
"This sounds interesting but I'd need to run it by Marcus (the owner). Can you send me some info I can share with him?"

Business: Elite Auto Repair
Role: Shop Manager
```

---

## Example 5: Pricing Question (Warm)

```
Email Classification: INTERESTED
Confidence: 75%

From: carlos@greenthumblandscaping.com
Subject: Re: Quote request form for Green Thumb
Received: 2 hours ago

Reply Content:
"I looked at your website. How much does this cost? We're a small operation and don't have a big budget for tech stuff."

Business: Green Thumb Landscaping
Industry: Landscaping
Location: Phoenix, AZ
Gap: No online quote form
Business Size: Small (probably solo or 2-3 person crew)
```

---

## Example 6: Fast Reply + Multiple Signals

```
Email Classification: INTERESTED
Confidence: 90%

From: sarah@sunshinedentalcare.com
Subject: RE: Online booking for Sunshine Dental
Received: 3 hours after outreach sent

Reply Content:
"Hi,

We've actually been looking at online booking systems for the past month. Our front desk is overwhelmed with phone calls and we're losing patients who want to book online.

A few questions:
- Does it sync with our practice management system (Dentrix)?
- Can patients request specific hygienists?
- What's the typical ROI your dental clients see?

I'm the practice manager and Dr. Smith has asked me to find a solution. Can we set up a call this week?

Sarah Chen
Practice Manager, Sunshine Dental Care
Direct: 813-555-2345"

Business: Sunshine Dental Care
Industry: Dental
Location: Tampa, FL
Gap: No online booking
Rating: 4.7 stars
```

---

## Example 7: Lukewarm Response

```
Email Classification: INTERESTED
Confidence: 60%

From: owner@localbusiness.com
Subject: Re: Your email
Received: Yesterday

Reply Content:
"Sounds good. Let me know more."

Business: Unknown local business
No other context available
Original Gap: No website
```

---

## Example 8: With Full Classification Output

```
=== CLASSIFICATION OUTPUT ===

## Email Classification

**From:** amanda@peakperformancefitness.com
**Subject:** Re: Member app for Peak Performance
**Received:** Today at 9:45 AM

## Classification: INTERESTED

**Confidence:** 88%

**Signals Detected:**
- ✅ Asks about pricing
- ✅ Mentions specific pain point (no-shows)
- ✅ Fast response (same day)
- ⚠️ Mentions budget constraints

**Intent Analysis:**
**What They Want:** Understand pricing and how it solves their no-show problem
**Decision Stage:** Consideration

=== END CLASSIFICATION ===

Additional Context:
Business: Peak Performance Fitness (Gym)
Owner: Amanda Chen
Location: San Diego, CA
Gap: No member app, no online class booking
They downloaded our guide "5 Ways Gyms Are Losing Members to Apps" last week

Please score this lead and provide action plan.
```

---

## Quick Input Template

```
Email Classification: [INTERESTED/QUESTION/OBJECTION]
Confidence: [X]%

From: [email]
Subject: [subject line]
Received: [when]

Reply Content:
"[Full email text]"

Context:
- Original Outreach Date: [when sent]
- Business: [name]
- Industry: [type]
- Location: [city, state]
- Gap: [what's missing]
- Decision Maker: [Yes/No/Unknown]
- Any other relevant context
```
