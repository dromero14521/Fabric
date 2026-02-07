# SaaS Business Patterns - Quick Reference

## 5 Flagship Patterns (Available Now)

| Pattern | Domain | Use When | Output |
|---------|--------|----------|--------|
| **create_outbound_sequence** | Client Acquisition | Need to generate B2B/B2C leads | 7-email sequence, LinkedIn messages, call scripts |
| **setup_payment_integration** | Technical | Building product with payments | Complete Stripe/PayPal integration code |
| **build_financial_model** | Business Strategy | Need investor materials or financial planning | 3-year projections, unit economics, scenarios |
| **create_winning_proposal** | Client Acquisition | Closing a client deal | High-converting proposal with ROI and pricing |
| **automate_lead_enrichment** | Automation | Too much manual lead research | Automated enrichment workflow with CRM integration |

---

## Usage Examples

### 1. Create Outbound Sequence
```bash
fabric --pattern create_outbound_sequence << EOF
Target industry: B2B SaaS (50-500 employees)
Value proposition: AI customer support automation (80% faster response)
Pain points: Long wait times, high costs, inconsistent quality
Social proof: Saved TechCorp $200k/year
CTA: Book 15-min demo
EOF
```

### 2. Setup Payment Integration
```bash
fabric --pattern setup_payment_integration << EOF
Payment provider: Stripe
Pricing model: Subscription (monthly/annual)
Tech stack: Next.js 14, TypeScript, PostgreSQL
Currencies: USD, EUR
Webhooks: payment.succeeded, subscription.updated
EOF
```

### 3. Build Financial Model
```bash
fabric --pattern build_financial_model << EOF
Business model: B2B SaaS
Pricing: $99/mo Pro, $299/mo Enterprise
Current: Pre-revenue, launching in 30 days
Target: $1M ARR by Month 24
COGS: $15/customer/month
Team: 2 founders, hire engineer Month 6 ($120k)
CAC: $500 → optimize to $200 by Month 12
Churn: 5% monthly target
EOF
```

### 4. Create Winning Proposal
```bash
fabric --pattern create_winning_proposal << EOF
Client: Acme Corp (e-commerce, 50 employees)
Project: Shopify inventory automation
Pain points:
- 10 hours/week manual updates ($500/week cost)
- $5k/month lost sales from stock-outs
- No real-time POS sync
Outcomes: Save 8 hours/week, reduce stock-outs 90%
Budget: $15k-$25k
Timeline: 10 weeks to launch
EOF
```

### 5. Automate Lead Enrichment
```bash
fabric --pattern automate_lead_enrichment << EOF
Lead source: Website form (Typeform)
CRM: HubSpot
Enrichment: Company size, industry, tech stack, email verification
Budget: $250/month
Volume: 500 leads/month
ICP: B2B SaaS, 50-500 employees, Salesforce/HubSpot users
Routing: >80 → AE, 60-79 → SDR, <60 → nurture
EOF
```

---

## Pattern Directory Structure

```
data/patterns/
│
├── client_acquisition/
│   ├── create_outbound_sequence/      ✅ Available
│   ├── create_winning_proposal/       ✅ Available
│   ├── generate_lead_magnet/          🔜 Coming Soon
│   ├── build_sales_funnel/            🔜 Coming Soon
│   └── qualify_leads/                 🔜 Coming Soon
│
├── technical_implementation/
│   ├── setup_payment_integration/     ✅ Available
│   ├── build_landing_page/            🔜 Coming Soon
│   ├── implement_analytics/           🔜 Coming Soon
│   ├── create_auth_system/            🔜 Coming Soon
│   └── design_database_schema/        🔜 Coming Soon
│
├── business_strategy/
│   ├── build_financial_model/         ✅ Available
│   ├── analyze_market_opportunity/    🔜 Coming Soon
│   ├── create_business_plan/          🔜 Coming Soon
│   └── optimize_pricing_strategy/     🔜 Coming Soon
│
├── automation/
│   ├── automate_lead_enrichment/      ✅ Available
│   ├── create_crm_workflow/           🔜 Coming Soon
│   ├── setup_customer_onboarding/     🔜 Coming Soon
│   └── automate_invoice_generation/   🔜 Coming Soon
│
└── _outcomes/                         🔜 Coming Soon
    ├── get_first_client/
    ├── launch_saas_mvp/
    ├── scale_to_10k_mrr/
    └── build_ai_agency/
```

---

## When to Use Each Pattern

### Getting Clients
- **Need leads?** → `create_outbound_sequence` (cold outreach)
- **Need to close?** → `create_winning_proposal` (convert prospects)
- **Need to nurture?** → `automate_lead_enrichment` (qualify faster)

### Building Products
- **Need payments?** → `setup_payment_integration` (Stripe/PayPal)
- **Need planning?** → `build_financial_model` (financials)
- **Need strategy?** → `build_financial_model` + business plan

### Scaling Operations
- **Too much manual work?** → `automate_lead_enrichment` (sales automation)
- **Need to hire/raise?** → `build_financial_model` (financial planning)

---

## Pattern Quality Checklist

Every pattern provides:
- ✅ **Immediate Action**: Copy-paste ready output
- ✅ **Business Value**: Clear ROI or time savings
- ✅ **Complete**: Nothing left to "figure out"
- ✅ **Realistic**: Industry benchmarks included
- ✅ **Tested**: Real-world scenarios, edge cases handled

---

## Tips for Best Results

### 1. Be Specific
❌ Bad: "I need a sales email"
✅ Good: "Target B2B SaaS directors, solve integration headaches, 3-day trial CTA"

### 2. Provide Context
❌ Bad: "Build financial model"
✅ Good: "B2B SaaS, $99/mo pricing, pre-revenue, targeting $500k ARR Year 1"

### 3. Include Numbers
❌ Bad: "Client has inefficient processes"
✅ Good: "Client wastes 10 hours/week, costing $500, losing $5k/mo in sales"

### 4. Define Outcomes
❌ Bad: "Make things better"
✅ Good: "Reduce customer support time by 60%, save $100k/year"

---

## Next Steps

1. **Try a Pattern**: Pick one from the 5 available
2. **Review Output**: Customize as needed for your situation
3. **Implement**: Use the output immediately in your business
4. **Provide Feedback**: Help us improve (see SAAS_PATTERNS_GUIDE.md)

---

## Full Documentation

- **Complete Guide**: See `SAAS_PATTERNS_GUIDE.md`
- **Pattern Details**: Check `user.md` in each pattern directory
- **Technical Specs**: Read `system.md` for prompt engineering

---

**Built for revenue. Optimized for action.**
