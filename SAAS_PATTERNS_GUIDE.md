# SaaS Business Patterns Guide

## Overview

Fabric now includes a comprehensive suite of **business-focused patterns** designed to help entrepreneurs, freelancers, agencies, and SaaS founders build, grow, and monetize their businesses using AI automation.

## New Pattern Structure

```
data/patterns/
├── client_acquisition/      # Get customers and close deals
├── technical_implementation/ # Build and deploy solutions
├── business_strategy/        # Plan and analyze business
├── automation/              # Scale operations with automation
├── marketing_sales/         # Market and sell effectively
├── product_development/     # Build and ship products
├── client_delivery/         # Deliver projects successfully
├── ai_agency/              # AI-specific service offerings
└── _outcomes/              # Quick-start outcome pathways [Coming Soon]
```

## Domain Descriptions

### 🎯 Client Acquisition
**Purpose**: Generate leads, qualify prospects, and close deals

**Patterns**:
- `create_outbound_sequence` - B2B sales email sequences with multi-channel touchpoints
- `create_winning_proposal` - Client proposals that convert at >40% close rate
- `generate_lead_magnet` - High-value content to capture leads [Coming Soon]
- `build_sales_funnel` - Complete funnel design and optimization [Coming Soon]
- `qualify_leads` - Lead qualification frameworks and scoring [Coming Soon]

**Use When**: You need to acquire new clients or customers

---

### 💻 Technical Implementation
**Purpose**: Build and deploy technical solutions (payments, auth, analytics, infrastructure)

**Patterns**:
- `setup_payment_integration` - Stripe/PayPal integration with best practices
- `build_landing_page` - Conversion-optimized landing pages [Coming Soon]
- `implement_analytics` - GA4, Mixpanel, custom tracking [Coming Soon]
- `create_auth_system` - Auth0, Clerk, custom authentication [Coming Soon]
- `design_database_schema` - Optimized database design [Coming Soon]

**Use When**: You're building a product or implementing client solutions

---

### 📊 Business Strategy
**Purpose**: Plan, analyze, and optimize business operations

**Patterns**:
- `build_financial_model` - 3-year projections with unit economics
- `analyze_market_opportunity` - Market sizing and validation [Coming Soon]
- `create_business_plan` - Investor-ready business plans [Coming Soon]
- `optimize_pricing_strategy` - Value-based pricing models [Coming Soon]

**Use When**: You need strategic clarity or investor materials

---

### 🤖 Automation
**Purpose**: Automate repetitive tasks and scale operations

**Patterns**:
- `automate_lead_enrichment` - Automated lead data enrichment with Clearbit, Apollo
- `create_crm_workflow` - CRM automation for HubSpot, Salesforce [Coming Soon]
- `setup_customer_onboarding` - Automated onboarding sequences [Coming Soon]
- `automate_invoice_generation` - Billing and invoicing automation [Coming Soon]

**Use When**: You want to save time or scale without hiring

---

### 📈 Marketing & Sales (Coming Soon)
**Purpose**: Create marketing assets, campaigns, and sales materials

**Planned Patterns**:
- `write_sales_copy` - Landing pages, emails, ad copy
- `create_email_campaign` - Email marketing campaigns
- `design_ad_creative` - Ad concepts and copy
- `optimize_seo_content` - SEO-optimized content
- `analyze_competitor_positioning` - Competitive intelligence

---

### 🚀 Product Development (Coming Soon)
**Purpose**: Design, build, and launch products

**Planned Patterns**:
- `design_saas_architecture` - SaaS technical architecture
- `create_mvp_spec` - Minimum viable product specifications
- `plan_feature_roadmap` - Product roadmap prioritization
- `design_onboarding_flow` - User onboarding UX

---

### 📦 Client Delivery (Coming Soon)
**Purpose**: Successfully deliver client projects

**Planned Patterns**:
- `scope_project` - Project scoping and estimation
- `create_sow` - Statement of Work documents
- `build_project_timeline` - Project plans and Gantt charts
- `generate_status_report` - Client status updates

---

### 🤖 AI Agency (Coming Soon)
**Purpose**: Build and sell AI services

**Planned Patterns**:
- `build_ai_service_offering` - Package AI services for clients
- `create_ai_consulting_package` - AI consulting frameworks
- `design_ai_workflow` - Custom AI workflow design
- `price_ai_services` - AI service pricing strategies
- `demonstrate_ai_roi` - ROI calculators for AI projects

---

## Flagship Patterns (Available Now)

### 1. Create Outbound Sequence
**Location**: `data/patterns/client_acquisition/create_outbound_sequence/`

Generate personalized B2B/B2C outbound sales sequences including:
- 7-email sequence with A/B test variations
- LinkedIn connection messages
- Cold call scripts
- Deliverability optimization
- CRM setup instructions

**Input**: Target industry, value prop, pain points, social proof
**Output**: Complete multi-channel outbound campaign

**Example Use**:
```bash
fabric --pattern create_outbound_sequence < my_outbound_brief.txt
```

---

### 2. Setup Payment Integration
**Location**: `data/patterns/technical_implementation/setup_payment_integration/`

Production-ready Stripe/PayPal integration including:
- Frontend payment forms (React, Next.js, Vue)
- Backend API endpoints with error handling
- Webhook handlers with signature verification
- Database schema for transactions
- Security checklist and testing guide

**Input**: Payment provider, pricing model, tech stack, compliance needs
**Output**: Copy-paste ready integration code

**Example Use**:
```bash
fabric --pattern setup_payment_integration << EOF
Payment provider: Stripe
Pricing model: Subscription (monthly/annual)
Tech stack: Next.js 14, TypeScript, PostgreSQL
Currencies: USD, EUR
Webhooks needed: payment.succeeded, subscription.updated
EOF
```

---

### 3. Build Financial Model
**Location**: `data/patterns/business_strategy/build_financial_model/`

Investor-grade financial projections including:
- 36-month P&L, cash flow statements
- Unit economics (CAC, LTV, LTV:CAC ratio)
- Scenario modeling (best/likely/worst case)
- Break-even analysis and runway calculation
- Sensitivity analysis and assumption validation

**Input**: Business model, pricing, COGS, operating expenses, growth assumptions
**Output**: Complete financial model with investor summary

**Example Use**:
```bash
fabric --pattern build_financial_model << EOF
Business model: B2B SaaS
Pricing: $99/month (Professional), $299/month (Enterprise)
Current state: Pre-revenue, launching next month
Target: $1M ARR by Month 24
COGS: $15/customer/month (hosting, APIs)
Team: 2 founders (deferred salary), will hire 1 engineer at Month 6
EOF
```

---

### 4. Create Winning Proposal
**Location**: `data/patterns/client_acquisition/create_winning_proposal/`

High-converting client proposals including:
- Executive summary with quantified ROI
- Phased project approach
- Good/Better/Best pricing packages
- Case studies and social proof
- Risk mitigation and guarantees

**Input**: Client details, project type, pain points, outcomes, budget range
**Output**: Ready-to-send proposal document

**Example Use**:
```bash
fabric --pattern create_winning_proposal << EOF
Client: Acme Corp (e-commerce, 50 employees)
Project: Custom Shopify app for inventory automation
Pain points:
- Manual inventory updates (10 hours/week)
- Frequent stock-outs causing lost sales ($5k/month)
- No real-time sync between POS and online store
Desired outcome: Automated inventory sync, reduce stock-outs by 90%
Budget: $15,000-$25,000
Timeline: 8-12 weeks
Decision maker: Director of Operations
EOF
```

---

### 5. Automate Lead Enrichment
**Location**: `data/patterns/automation/automate_lead_enrichment/`

Automated lead enrichment workflows including:
- Company data enrichment (Clearbit, Apollo)
- Email verification (Hunter.io)
- Tech stack detection (BuiltWith)
- Lead scoring (ICP fit)
- CRM integration and routing

**Input**: Lead source, CRM system, enrichment needs, budget, ICP criteria
**Output**: Complete automation workflow with cost analysis

**Example Use**:
```bash
fabric --pattern automate_lead_enrichment << EOF
Lead source: Website contact form
CRM: HubSpot
Enrichment needed: Company size, industry, revenue, tech stack, email verification
Budget: Up to $250/month
Volume: ~500 leads/month
ICP: B2B SaaS companies, 50-500 employees, using Salesforce or HubSpot
Sales workflow: Auto-assign to AE if score >80, SDR if 60-80, nurture if <60
EOF
```

---

## How to Use These Patterns

### Basic Usage
```bash
# Interactive input
fabric --pattern <pattern_name>

# Pipe from file
fabric --pattern <pattern_name> < input.txt

# Inline input
fabric --pattern <pattern_name> << EOF
[Your input here]
EOF
```

### Advanced: Chaining Patterns
```bash
# Generate financial model, then create investor pitch
fabric --pattern build_financial_model < business_details.txt > financial_model.md
fabric --pattern create_investor_pitch < financial_model.md > pitch.md
```

### Integration with Existing Workflows
```bash
# Export to your CRM
fabric --pattern create_outbound_sequence < brief.txt | pbcopy

# Generate and commit
fabric --pattern setup_payment_integration < spec.txt > src/payment.ts
git add src/payment.ts
git commit -m "Add Stripe integration"
```

---

## Pattern Quality Standards

Every pattern in the new structure follows these principles:

### ✅ Actionable Output
- All outputs are ready to use immediately (copy-paste, send to client, implement)
- No generic advice; specific, detailed, customized results
- Include code, documents, or frameworks that work out-of-the-box

### ✅ Business Value Focus
- Every pattern connects to revenue (getting clients, closing deals, delivering value)
- Outputs quantify impact (ROI, time saved, revenue increased)
- Optimized for real business scenarios, not academic exercises

### ✅ Industry Best Practices
- Follow proven frameworks (sales methodologies, technical standards, financial modeling best practices)
- Include benchmarks and validation (industry averages, realistic assumptions)
- Security, compliance, and quality built-in

### ✅ Comprehensive & Complete
- Nothing left to "figure out later"
- Edge cases handled (errors, failures, alternatives)
- Testing, deployment, and maintenance included

### ✅ Optimized for Skimmability
- Clear structure with headers, bullets, tables
- Key information highlighted
- Executive summaries for busy readers
- Visual elements (diagrams, workflows) where helpful

---

## Coming Soon: Outcome Pathways

The `_outcomes/` directory will provide guided, multi-pattern workflows for common business goals:

### Planned Outcome Pathways

**Get First Client** (Days 0-30)
1. Define ICP and value proposition
2. Generate lead magnet
3. Create outbound sequence
4. Build simple landing page
5. Create winning proposal
6. Set up payment integration

**Launch SaaS MVP** (Days 0-90)
1. Validate market opportunity
2. Build financial model
3. Design SaaS architecture
4. Create MVP spec and roadmap
5. Set up authentication and payments
6. Implement analytics
7. Design onboarding flow

**Scale to $10k MRR** (Months 3-6)
1. Optimize pricing strategy
2. Build sales funnel
3. Automate lead enrichment
4. Create email campaigns
5. Analyze and optimize conversion
6. Productize service offering

**Automate Operations** (Ongoing)
1. Audit manual processes
2. Create CRM workflows
3. Automate customer onboarding
4. Set up reporting dashboards
5. Automate invoicing and billing

**Build AI Agency** (Days 0-60)
1. Build AI service offering
2. Create AI consulting package
3. Design demonstration workflows
4. Price AI services
5. Create ROI calculators
6. Package thought leadership content

---

## Roadmap

### Phase 1: Foundation ✅ COMPLETE
- [x] New directory structure
- [x] 5 flagship patterns across domains
- [x] Documentation and guides

### Phase 2: Core Business Patterns (Next 4 Weeks)
- [ ] Client Acquisition: 5 patterns total
- [ ] Technical Implementation: 5 patterns total
- [ ] Business Strategy: 4 patterns total
- [ ] Automation: 4 patterns total

### Phase 3: Outcome Pathways (Weeks 5-8)
- [ ] Get First Client pathway
- [ ] Launch SaaS MVP pathway
- [ ] Scale to $10k MRR pathway
- [ ] Automate Operations pathway
- [ ] Build AI Agency pathway

### Phase 4: Advanced & Integration (Weeks 9-12)
- [ ] Marketing & Sales: 5 patterns
- [ ] Product Development: 4 patterns
- [ ] Client Delivery: 4 patterns
- [ ] AI Agency: 5 patterns
- [ ] Integration guides (CRM, payment processors, analytics tools)

---

## Feedback & Contributions

We're actively building this new structure. Your feedback shapes the roadmap.

**Request a Pattern**: Open an issue with:
- Domain (client acquisition, automation, etc.)
- Use case (what you're trying to accomplish)
- Expected input and output
- Business context (agency, SaaS, consulting, etc.)

**Contribute a Pattern**: Follow the existing pattern structure:
1. Create directory in appropriate domain
2. Write comprehensive `system.md` following flagship pattern format
3. Include `user.md` if needed (usually empty)
4. Submit PR with example usage

**Report Issues**: If a pattern produces low-quality output:
1. Share your input (sanitize any sensitive data)
2. Describe expected vs. actual output
3. Include business context for better debugging

---

## Migrating from Old Patterns

### Old Pattern Structure
The original Fabric patterns (e.g., `analyze_paper`, `create_quiz`, `explain_code`) remain available and unchanged. They serve different use cases:
- **Old patterns**: General-purpose AI tasks (analysis, explanation, creation)
- **New patterns**: Business-specific automation (revenue-focused)

### Using Both
You can use both old and new patterns:
```bash
# Old pattern: Analyze a technical paper
fabric --pattern analyze_paper < research.pdf

# New pattern: Create financial model for your SaaS
fabric --pattern build_financial_model < business_details.txt
```

### No Breaking Changes
All existing patterns work exactly as before. The new structure is additive.

---

## Support

**Questions?**
- Read pattern `system.md` for detailed instructions
- Check examples in this guide
- Review existing pattern outputs for reference

**Common Issues**:
- **Pattern not found**: Ensure you're using the full path or check available patterns with `fabric --list`
- **Low-quality output**: Provide more detailed input (see pattern's INPUT section for required fields)
- **Integration issues**: Check API documentation and credentials

---

## Philosophy

These patterns embody a core principle: **AI should directly contribute to business outcomes, not just automate busy work.**

Every pattern answers: "How does this help me make money, save time, or reduce risk?"

We optimize for:
1. **Speed to value**: <1 hour from pattern run to actionable output
2. **Revenue impact**: Patterns should enable $X in new revenue or $Y in cost savings
3. **Real-world applicability**: Built from actual business scenarios, not theoretical frameworks
4. **Compound value**: Patterns work together (financial model → proposal → sales sequence → automation)

---

**Built for entrepreneurs, by entrepreneurs.**

Welcome to the future of AI-powered business building.
