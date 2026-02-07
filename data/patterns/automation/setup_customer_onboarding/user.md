# Example Inputs for setup_customer_onboarding

Use one of the following input formats to design an automated customer onboarding system:

---

## Example 1: SaaS Product (B2B)

```
Product: ProjectFlow - Project Management SaaS
Type: B2B SaaS, subscription model
Pricing: $29/user/month (Starter), $79/user/month (Pro), Custom (Enterprise)

Target Customers:
- SMB: 5-50 employees, self-service signup
- Mid-Market: 50-500 employees, sales-assisted
- Enterprise: 500+ employees, high-touch sales

Current Onboarding Issues:
- 40% of trial users never complete setup
- Average time to first project creation: 5 days (too slow)
- Day 30 retention: only 35%
- CSM team is overwhelmed with manual onboarding calls

"Aha Moment": When user creates their first project and assigns tasks to team members

Current Process:
1. User signs up for 14-day trial
2. Welcome email sent (generic)
3. User lands on empty dashboard
4. No guidance, users get lost
5. CSM manually reaches out to enterprise leads

Team:
- 3 CSMs handling 200+ accounts each
- No dedicated onboarding specialist
- Using HubSpot for email, Intercom for chat

Goals:
- Reduce time to first project to under 2 days
- Increase Day 30 retention to 50%
- Automate 80% of SMB onboarding
- Free up CSM time for enterprise accounts
```

---

## Example 2: Mobile App (B2C)

```
Product: FitTrack - Fitness tracking mobile app
Type: B2C, freemium model
Pricing: Free (basic), $9.99/month (Premium), $79.99/year (Premium Annual)

Target Users:
- Casual fitness enthusiasts (25-45 years old)
- Want to track workouts and nutrition
- 60% iOS, 40% Android

Current Onboarding Issues:
- 70% of users download but never complete profile setup
- Most users don't log their first workout
- Day 7 retention: only 20%
- Premium conversion rate: 2% (industry avg is 5%)

"Aha Moment": When user completes first workout and sees calories burned + progress chart

Current Process:
1. User downloads app
2. Account creation (email or social)
3. Basic profile setup (weight, height, goals)
4. Lands on home screen with no guidance
5. Push notifications are generic and annoying

Goals:
- Get 50% of users to log first workout within 24 hours
- Increase Day 7 retention to 40%
- Increase premium conversion to 5%
- Reduce uninstall rate in first week

Available Tools:
- Firebase for push notifications
- Braze for email/push automation
- Mixpanel for analytics
```

---

## Example 3: E-commerce Platform (Marketplace)

```
Platform: CraftMarket - Handmade goods marketplace (like Etsy)
Type: Two-sided marketplace
Revenue Model:
- Sellers: 5% transaction fee + $0.20 listing fee
- Buyers: Free to use

Onboarding Focus: SELLER onboarding (critical for marketplace growth)

Target Sellers:
- Hobbyist crafters looking to monetize
- Small business artisans
- Vintage/antique sellers

Current Seller Onboarding Issues:
- 60% of sellers never list their first product
- Average time to first listing: 14 days (way too long)
- Sellers get confused by shipping settings
- Photography quality is poor (hurts conversion)
- 50% of new sellers churn within 60 days

"Aha Moment": When seller makes their first sale

Current Process:
1. Seller signs up
2. Email verification
3. Long profile setup form (too many fields)
4. Shop settings (confusing)
5. Payment/tax setup (intimidating)
6. Finally can list products
7. No guidance on photography, pricing, or SEO

Goals:
- Reduce time to first listing to under 3 days
- Increase % of sellers listing first product to 70%
- Reduce 60-day seller churn to 30%
- Improve listing quality (photos, descriptions)

Available Resources:
- 2 seller success managers (can't scale)
- Help center with articles (low engagement)
- Facebook seller community (active but unmoderated)
```

---

## Example 4: Professional Services (Consulting)

```
Business: StrategyPro - Management Consulting Firm
Type: B2B Professional Services
Engagement Types:
- Strategy projects ($50k-200k, 3-6 months)
- Fractional COO services ($10k/month retainer)
- Workshop facilitation ($5k-15k per session)

Client Onboarding Focus: New retainer and project clients

Current Client Onboarding Issues:
- Inconsistent experience across different partners
- Clients don't know what to expect in week 1
- Kickoff meetings are disorganized
- Clients often don't provide required documents on time
- Scope creep starts early due to unclear boundaries

"Aha Moment": When client sees first deliverable (strategy deck or workshop output)

Current Process:
1. Contract signed
2. Partner sends personal welcome email (inconsistent)
3. Kickoff call scheduled (often delayed)
4. Client supposed to send documents (they forget)
5. Week 1 is often wasted on admin

Goals:
- Standardize onboarding across all partners
- Get all client documents collected before kickoff
- Deliver first value within 7 days
- Set clear expectations and boundaries upfront
- Create "white glove" experience for premium clients

Team:
- 5 partners
- 3 project managers
- Using Notion for project management
- No CRM (using spreadsheets)
```

---

## Example 5: Online Course / Education

```
Product: CodeMaster Academy - Online coding bootcamp
Type: EdTech, cohort-based courses
Pricing: $2,000-5,000 per course (6-12 weeks)

Target Students:
- Career changers (25-40 years old)
- Busy professionals learning to code
- Mix of self-paced and live sessions

Current Onboarding Issues:
- 20% of students never attend first live session
- Students don't complete pre-work before cohort starts
- Discord community is confusing for new students
- Technical setup (IDE, Git, etc.) causes frustration
- Week 1 has highest dropout rate

"Aha Moment": When student successfully runs their first code and sees output

Current Process:
1. Student purchases course
2. Welcome email with login credentials
3. Access to course portal (overwhelming)
4. Pre-work assigned (low completion)
5. Cohort starts, students are at different levels
6. First live session, many students unprepared

Goals:
- 95% pre-work completion before cohort start
- 90% attendance at first live session
- All students complete technical setup before Day 1
- Build community engagement in Discord
- Reduce Week 1 dropout to under 5%

Tools Available:
- Teachable for course hosting
- Discord for community
- Zoom for live sessions
- ConvertKit for email
```

---

## Example 6: API / Developer Platform

```
Product: DataSync API - Real-time data synchronization platform
Type: Developer tool / API platform
Pricing:
- Free tier: 10k API calls/month
- Starter: $49/month (100k calls)
- Growth: $199/month (1M calls)
- Enterprise: Custom

Target Users:
- Backend developers at startups
- Tech leads evaluating tools
- Enterprise architects

Current Onboarding Issues:
- Developers sign up but never make first API call
- Documentation is comprehensive but overwhelming
- No interactive tutorials or sandboxes
- Support tickets are high for basic integration questions
- Time to first successful integration: 7 days average

"Aha Moment": When developer makes first successful API call and sees data sync

Current Process:
1. Developer signs up
2. API key generated
3. Directed to docs (100+ pages)
4. Developer tries to integrate on their own
5. Gets stuck, files support ticket
6. Support helps, developer finally integrates

Goals:
- Reduce time to first API call to under 1 hour
- 50% of developers complete quickstart on Day 1
- Reduce basic support tickets by 70%
- Increase free-to-paid conversion from 3% to 8%
- Build developer community and advocacy

Available Tools:
- Segment for event tracking
- Intercom for in-app messaging
- Readme.io for docs
- Postman for API testing
```

---

## Quick Input Template

```
Product/Service Name: [Name]
Type: [SaaS / App / Marketplace / Service / Platform / Education]
Pricing Model: [Free / Freemium / Subscription / One-time / Usage-based]

Target Customers:
- Segment 1: [Description]
- Segment 2: [Description]

Current Onboarding Issues:
- [Issue 1]
- [Issue 2]
- [Issue 3]

"Aha Moment" Definition: [What action/realization = value delivered?]

Current Process:
1. [Step 1]
2. [Step 2]
3. [Step 3]

Current Metrics (if known):
- Signup to activation rate: [X]%
- Time to first value: [X] days
- Day 7 retention: [X]%
- Day 30 retention: [X]%

Goals:
- [Goal 1]
- [Goal 2]
- [Goal 3]

Team Structure:
- [Customer Success team size]
- [Available tools/platforms]
```
