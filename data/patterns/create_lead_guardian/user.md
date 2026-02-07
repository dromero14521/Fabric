# Example Inputs for create_lead_guardian

Use one of the following input formats to design a Lead Guardian AI agent:

---

## Example 1: Plumbing Company

```
Business Type: Emergency Plumbing Service
Business Name: RapidFlow Plumbing
Location: Phoenix, AZ metro area
Service Hours: 24/7 emergency, 7am-6pm scheduled

Services Offered:
- Emergency repairs (burst pipes, flooding, no hot water)
- Drain cleaning
- Water heater installation/repair
- Sewer line services
- Fixture installation

Average Job Values:
- Emergency call: $250-500
- Drain cleaning: $150-300
- Water heater: $1,200-3,000

Lead Sources to Cover:
- Website chat widget
- SMS inquiries
- After-hours phone (voicemail transcription)
- Facebook Messenger

Typical Customer Scenarios:
- "My toilet is overflowing!"
- "No hot water this morning"
- "Kitchen sink is completely clogged"
- "I see water coming from my ceiling"
- "How much do you charge for..."

What the Agent Should NOT Do:
- Don't give exact prices (too variable)
- Don't diagnose complex issues
- Don't promise specific arrival times

Booking Goal: Get customer's name, phone, address, and issue description → Schedule or dispatch tech
```

---

## Example 2: Dental Practice

```
Business Type: Family Dental Practice
Business Name: Bright Smile Dental
Location: Austin, TX
Service Hours: Mon-Fri 8am-5pm, Sat 9am-2pm

Services Offered:
- Routine cleanings and exams
- Teeth whitening
- Invisalign
- Crowns and bridges
- Emergency dental care
- Pediatric dentistry

Insurance: Accept most major plans, offer payment plans

Lead Sources to Cover:
- Website appointment request form
- Phone calls (voicemail after hours)
- Google Business Messages
- SMS inquiries

Typical Customer Scenarios:
- "Do you accept Delta Dental?"
- "I have a toothache, can I come in today?"
- "How much is a cleaning without insurance?"
- "Do you see kids?"
- "I want to schedule a whitening consultation"

What the Agent Should NOT Do:
- Don't diagnose dental issues
- Don't promise insurance coverage (must verify)
- Don't give treatment cost quotes (need exam first)

Booking Goal: Capture patient info (name, phone, DOB, insurance) → Schedule appropriate appointment type
```

---

## Example 3: Law Firm

```
Business Type: Personal Injury Law Firm
Business Name: Johnson & Associates
Location: Atlanta, GA
Practice Areas: Personal injury, car accidents, slip and fall, medical malpractice

Free Consultation: Yes, always
Fee Structure: Contingency (no fee unless we win)

Lead Sources to Cover:
- Website contact form
- Phone intake (after hours)
- Live chat
- SMS

Typical Customer Scenarios:
- "I was in a car accident last week"
- "I slipped and fell at a store"
- "My doctor made a mistake during surgery"
- "The insurance company is offering me a settlement, should I take it?"
- "How much is my case worth?"

What the Agent Should NOT Do:
- Don't give legal advice
- Don't estimate case value
- Don't make promises about outcomes
- Don't discuss other law firms

Intake Goal: Capture name, phone, email, brief description of incident, date of incident → Schedule free consultation

Urgency Indicators (flag for immediate callback):
- Statute of limitations approaching
- Currently in hospital
- Dealing with insurance adjuster today
```

---

## Example 4: HVAC Company

```
Business Type: Heating & Air Conditioning
Business Name: ComfortAir Solutions
Location: Dallas-Fort Worth, TX
Service Hours: Mon-Sat 7am-7pm, Emergency 24/7

Services Offered:
- AC repair and maintenance
- Heating repair and maintenance
- New system installation
- Duct cleaning
- Indoor air quality
- Smart thermostat installation

Seasonal Considerations:
- Summer: AC emergencies are urgent
- Winter: Heating failures are urgent
- Shoulder seasons: Maintenance and tune-ups

Lead Sources to Cover:
- Website chat
- Phone (overflow and after-hours)
- Text/SMS
- Nextdoor messages

Typical Customer Scenarios:
- "My AC stopped working and it's 100 degrees!"
- "Weird smell coming from my vents"
- "How much for a new AC unit?"
- "Do you offer financing?"
- "I need my annual tune-up scheduled"

What the Agent Should NOT Do:
- Don't quote prices for new systems (requires in-home assessment)
- Don't diagnose complex issues remotely
- Don't make guarantees on repair timelines

Booking Goal: Name, phone, address, service type, system age (if known), urgency level → Schedule or dispatch
```

---

## Example 5: Real Estate Agent

```
Business Type: Residential Real Estate Agent
Business Name: Sarah Chen Realty
Location: San Diego, CA
Specialties: First-time buyers, luxury homes, investment properties

Services Offered:
- Buyer representation
- Seller listing services
- Investment property consulting
- Relocation assistance

Lead Sources to Cover:
- Website inquiry forms
- Zillow/Realtor.com leads
- Text messages
- Instagram DMs
- Open house sign-ins

Typical Customer Scenarios:
- "I'm looking to buy my first home"
- "What's my home worth?"
- "I'm relocating from out of state"
- "I saw your listing at 123 Main St"
- "How's the market right now?"

What the Agent Should NOT Do:
- Don't give specific valuations (need proper CMA)
- Don't discuss other agents' listings negatively
- Don't make promises about sale prices or timelines

Goal: Capture name, phone, email, timeline, budget/price range, areas of interest → Schedule consultation call

Qualification Questions:
- Are you pre-approved for a mortgage?
- What's your timeline for buying/selling?
- Are you working with another agent?
```

---

## Example 6: Gym / Fitness Studio

```
Business Type: Boutique Fitness Studio
Business Name: CoreFit Studio
Location: Denver, CO
Class Types: HIIT, yoga, spin, strength training, barre

Pricing:
- Drop-in: $25/class
- 10-class pack: $200
- Unlimited monthly: $149
- First class free for new members

Lead Sources to Cover:
- Website chat
- Instagram DMs
- Text inquiries
- Missed call follow-up

Typical Customer Scenarios:
- "What classes do you offer?"
- "I'm a beginner, is this too hard for me?"
- "Do you have early morning classes?"
- "What's included in the membership?"
- "Can I try a class before joining?"

What the Agent Should NOT Do:
- Don't pressure into long-term commitments
- Don't make fitness promises (results vary)
- Don't share member information

Goal: Name, email, phone, fitness goals, experience level → Book free trial class

Promotions to Mention:
- First class always free
- Bring a friend = both get 50% off
- New member special: First month $99
```

---

## Example 7: SaaS / Software Company

```
Business Type: B2B SaaS Product
Business Name: DataSync Pro
Product: Real-time data integration platform
Target: Mid-market companies, IT teams, data engineers

Pricing:
- Starter: $199/month
- Professional: $499/month
- Enterprise: Custom

Lead Sources to Cover:
- Website chat widget
- Demo request form
- Trial signup follow-up
- Support inquiries from prospects

Typical Customer Scenarios:
- "Does this integrate with Salesforce?"
- "How is this different from [competitor]?"
- "Can I get a demo?"
- "What's the pricing for 50 users?"
- "Do you have SOC 2 compliance?"
- "I signed up for a trial but I'm stuck"

What the Agent Should NOT Do:
- Don't share proprietary technical details
- Don't trash talk competitors
- Don't give custom pricing (sales team handles)
- Don't make security claims without documentation

Goal: Name, email, company, role, use case, company size → Route to sales (enterprise) or self-service (SMB)

Handoff Triggers (connect to human):
- Enterprise-size company (500+ employees)
- Security/compliance questions
- Technical deep-dive requests
- Pricing negotiation
```

---

## Quick Input Template

```
Business Type: [e.g., Plumber, Dentist, Lawyer, SaaS]
Business Name: [Your business name]
Location: [City, State or "Online"]
Service Hours: [When are you available?]

Services Offered:
- [Service 1]
- [Service 2]
- [Service 3]

Lead Sources to Cover:
- [Channel 1: Website chat, SMS, etc.]
- [Channel 2]
- [Channel 3]

Typical Customer Scenarios:
- "[Example inquiry 1]"
- "[Example inquiry 2]"
- "[Example inquiry 3]"

What the Agent Should NOT Do:
- [Limitation 1 - e.g., don't give prices]
- [Limitation 2 - e.g., don't diagnose]
- [Limitation 3 - e.g., don't promise timelines]

Booking/Conversion Goal:
[What info do you need? What action should they take?]

Urgency Indicators (if applicable):
- [When should someone call back immediately?]

Promotions/Offers to Mention:
- [Any current offers the agent should share?]
```
