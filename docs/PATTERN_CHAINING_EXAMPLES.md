# Pattern Chaining Examples

Comprehensive examples of chaining Fabric patterns together for complex business workflows.

---

## Table of Contents

1. [Chaining Fundamentals](#chaining-fundamentals)
2. [Prospecting to Outreach Pipeline](#prospecting-to-outreach-pipeline)
3. [Full Sales Cycle Workflow](#full-sales-cycle-workflow)
4. [Inbox Automation Pipeline](#inbox-automation-pipeline)
5. [Client Onboarding Workflow](#client-onboarding-workflow)
6. [Lead Magnet to Funnel Pipeline](#lead-magnet-to-funnel-pipeline)
7. [Business Launch Workflow](#business-launch-workflow)
8. [Revenue Optimization Pipeline](#revenue-optimization-pipeline)
9. [Automation Scripts](#automation-scripts)
10. [Advanced Multi-Pattern Workflows](#advanced-multi-pattern-workflows)

---

## Chaining Fundamentals

### Basic Chaining Syntax

```bash
# Pipe output from one pattern to another
pattern1 | pattern2 | pattern3

# Save intermediate results
pattern1 > step1.txt && cat step1.txt | pattern2 > step2.txt

# Use tee to save and continue
pattern1 | tee step1.txt | pattern2 > step2.txt
```

### Chaining Best Practices

1. **Save intermediate outputs** - Useful for debugging and reprocessing
2. **Use descriptive filenames** - Include date and context
3. **Create bash scripts** - For repeatable workflows
4. **Test each step** - Verify output before piping to next pattern

---

## Prospecting to Outreach Pipeline

### Overview

```
scrape_local_businesses → analyze_business_gaps → personalize_from_gaps → draft_cold_email → draft_followup_sequence
```

### Complete Workflow

```bash
#!/bin/bash
# Prospecting to Outreach Pipeline
# Usage: ./prospect_to_outreach.sh "plumbers" "Austin, TX"

VERTICAL=$1
LOCATION=$2
DATE=$(date +%Y-%m-%d)
OUTPUT_DIR="outreach_${DATE}"

mkdir -p $OUTPUT_DIR

echo "=== Step 1: Finding prospects ==="
echo "Find $VERTICAL in $LOCATION without online booking" | \
  fabric -p scrape_local_businesses > "$OUTPUT_DIR/1_prospects.txt"

echo "=== Step 2: Analyzing gaps for top prospects ==="
# Extract top 10 prospects and analyze each
head -50 "$OUTPUT_DIR/1_prospects.txt" | \
  fabric -p analyze_business_gaps > "$OUTPUT_DIR/2_gap_analysis.txt"

echo "=== Step 3: Creating personalized copy ==="
cat "$OUTPUT_DIR/2_gap_analysis.txt" | \
  fabric -p personalize_from_gaps > "$OUTPUT_DIR/3_copy_kit.txt"

echo "=== Step 4: Drafting cold emails ==="
cat "$OUTPUT_DIR/3_copy_kit.txt" | \
  fabric -p draft_cold_email > "$OUTPUT_DIR/4_cold_emails.txt"

echo "=== Step 5: Creating follow-up sequences ==="
cat "$OUTPUT_DIR/4_cold_emails.txt" | \
  fabric -p draft_followup_sequence > "$OUTPUT_DIR/5_followup_sequences.txt"

echo "=== Pipeline complete! ==="
echo "Output saved to: $OUTPUT_DIR/"
ls -la "$OUTPUT_DIR/"
```

### Step-by-Step Breakdown

#### Step 1: Find Prospects
```bash
echo "Find plumbers in Austin, TX without online booking,
limit 50, include Google Maps listings" | fabric -p scrape_local_businesses

# Output: Tiered prospect list with scores
```

#### Step 2: Analyze Gaps
```bash
cat prospects.txt | fabric -p analyze_business_gaps

# Output: Gap analysis with revenue impact for each prospect
```

#### Step 3: Create Copy
```bash
cat gap_analysis.txt | fabric -p personalize_from_gaps

# Output: 15+ copy snippets per prospect
```

#### Step 4: Draft Emails
```bash
cat copy_kit.txt | fabric -p draft_cold_email

# Output: 5 subject lines + 3 email versions per prospect
```

#### Step 5: Create Follow-ups
```bash
cat cold_emails.txt | fabric -p draft_followup_sequence

# Output: 5-email sequence per prospect
```

---

## Full Sales Cycle Workflow

### Overview

```
┌─────────────────────────────────────────────────────────────────────────┐
│                        FULL SALES CYCLE                                 │
├─────────────────────────────────────────────────────────────────────────┤
│                                                                         │
│  DISCOVERY                                                              │
│  └── scrape_local_businesses → analyze_business_gaps                    │
│              ↓                                                          │
│  OUTREACH                                                               │
│  └── personalize_from_gaps → draft_cold_email → draft_followup_sequence│
│              ↓                                                          │
│  RESPONSE HANDLING                                                      │
│  └── classify_email_reply → flag_hot_lead → draft_reply                │
│              ↓                                                          │
│  QUALIFICATION                                                          │
│  └── qualify_leads                                                      │
│              ↓                                                          │
│  CLOSING                                                                │
│  └── create_winning_proposal                                            │
│              ↓                                                          │
│  DELIVERY                                                               │
│  └── audit_business_website → create_lead_guardian                     │
│                                                                         │
└─────────────────────────────────────────────────────────────────────────┘
```

### Complete Script

```bash
#!/bin/bash
# Full Sales Cycle - From Prospect to Client
# Usage: ./full_sales_cycle.sh

PROSPECT_FILE=$1
DATE=$(date +%Y-%m-%d)
CYCLE_DIR="sales_cycle_${DATE}"

mkdir -p "$CYCLE_DIR"/{discovery,outreach,responses,qualification,closing,delivery}

# === DISCOVERY PHASE ===
echo "=== DISCOVERY: Analyzing prospect ==="
cat "$PROSPECT_FILE" | fabric -p analyze_business_gaps > "$CYCLE_DIR/discovery/gaps.txt"

# === OUTREACH PHASE ===
echo "=== OUTREACH: Creating campaign ==="
cat "$CYCLE_DIR/discovery/gaps.txt" | \
  fabric -p personalize_from_gaps > "$CYCLE_DIR/outreach/copy.txt"

cat "$CYCLE_DIR/outreach/copy.txt" | \
  fabric -p draft_cold_email > "$CYCLE_DIR/outreach/initial_email.txt"

cat "$CYCLE_DIR/outreach/initial_email.txt" | \
  fabric -p draft_followup_sequence > "$CYCLE_DIR/outreach/sequence.txt"

echo "Outreach campaign ready in: $CYCLE_DIR/outreach/"

# === When response comes in ===
# Save response to $CYCLE_DIR/responses/reply.txt, then:
#
# cat "$CYCLE_DIR/responses/reply.txt" | fabric -p classify_email_reply > "$CYCLE_DIR/responses/classified.txt"
# cat "$CYCLE_DIR/responses/classified.txt" | fabric -p flag_hot_lead > "$CYCLE_DIR/responses/scored.txt"
# cat "$CYCLE_DIR/responses/scored.txt" | fabric -p draft_reply > "$CYCLE_DIR/responses/my_reply.txt"

# === QUALIFICATION PHASE ===
# After discovery call:
#
# cat discovery_notes.txt | fabric -p qualify_leads > "$CYCLE_DIR/qualification/qualified.txt"

# === CLOSING PHASE ===
# If qualified:
#
# cat "$CYCLE_DIR/qualification/qualified.txt" | fabric -p create_winning_proposal > "$CYCLE_DIR/closing/proposal.txt"

# === DELIVERY PHASE ===
# After closed won:
#
# echo "https://clientwebsite.com" | fabric -p audit_business_website > "$CYCLE_DIR/delivery/audit.txt"
# cat client_details.txt | fabric -p create_lead_guardian > "$CYCLE_DIR/delivery/agent.txt"
```

---

## Inbox Automation Pipeline

### Overview

```
New Email → classify_email_reply → flag_hot_lead → draft_reply
```

### Email Processing Script

```bash
#!/bin/bash
# Inbox Automation Pipeline
# Usage: ./process_inbox.sh emails_directory/

INBOX_DIR=$1
DATE=$(date +%Y-%m-%d)
OUTPUT_DIR="inbox_processed_${DATE}"

mkdir -p "$OUTPUT_DIR"/{hot,warm,nurture,disqualified,replies}

process_email() {
    local email_file=$1
    local basename=$(basename "$email_file" .txt)

    echo "Processing: $email_file"

    # Step 1: Classify
    classification=$(cat "$email_file" | fabric -p classify_email_reply)
    echo "$classification" > "$OUTPUT_DIR/${basename}_classified.txt"

    # Step 2: Extract category
    category=$(echo "$classification" | grep -o "INTERESTED\|QUESTION\|OBJECTION\|NOT_INTERESTED\|AUTO_REPLY\|SPAM")

    # Step 3: Score if worth pursuing
    if [[ "$category" == "INTERESTED" || "$category" == "QUESTION" ]]; then
        score_result=$(cat "$email_file" | fabric -p flag_hot_lead)
        echo "$score_result" > "$OUTPUT_DIR/${basename}_scored.txt"

        # Extract tier
        tier=$(echo "$score_result" | grep -o "HOT\|WARM\|NURTURE\|LOW")

        # Step 4: Draft reply
        reply=$(cat "$email_file" | fabric -p draft_reply)

        case $tier in
            "HOT")
                echo "$reply" > "$OUTPUT_DIR/hot/${basename}_reply.txt"
                echo "🔥 HOT LEAD: $basename - Reply ready!"
                ;;
            "WARM")
                echo "$reply" > "$OUTPUT_DIR/warm/${basename}_reply.txt"
                echo "🌡️ WARM LEAD: $basename"
                ;;
            "NURTURE")
                echo "$reply" > "$OUTPUT_DIR/nurture/${basename}_reply.txt"
                echo "📧 NURTURE: $basename"
                ;;
            *)
                echo "$reply" > "$OUTPUT_DIR/disqualified/${basename}_reply.txt"
                echo "❌ LOW PRIORITY: $basename"
                ;;
        esac
    elif [[ "$category" == "OBJECTION" ]]; then
        # Handle objection with draft_reply
        reply=$(echo "$email_file
Context: This is an objection that needs handling" | fabric -p draft_reply)
        echo "$reply" > "$OUTPUT_DIR/replies/${basename}_objection_reply.txt"
        echo "⚠️ OBJECTION: $basename - Reply ready!"
    else
        echo "⏭️ SKIPPED: $basename ($category)"
    fi
}

# Process all emails
for email in "$INBOX_DIR"/*.txt; do
    if [[ -f "$email" ]]; then
        process_email "$email"
    fi
done

echo ""
echo "=== INBOX PROCESSING COMPLETE ==="
echo "Hot leads: $(ls -1 $OUTPUT_DIR/hot/ 2>/dev/null | wc -l)"
echo "Warm leads: $(ls -1 $OUTPUT_DIR/warm/ 2>/dev/null | wc -l)"
echo "Nurture: $(ls -1 $OUTPUT_DIR/nurture/ 2>/dev/null | wc -l)"
echo ""
echo "HOT LEADS (respond within 1 hour):"
ls -1 "$OUTPUT_DIR/hot/" 2>/dev/null || echo "None"
```

---

## Client Onboarding Workflow

### Overview

```
create_winning_proposal (closed won) → audit_business_website → create_lead_guardian → setup_customer_onboarding → automate_task
```

### Onboarding Script

```bash
#!/bin/bash
# Client Onboarding Workflow
# Usage: ./onboard_client.sh client_info.txt

CLIENT_FILE=$1
CLIENT_NAME=$(head -1 "$CLIENT_FILE" | cut -d: -f2 | xargs)
DATE=$(date +%Y-%m-%d)
CLIENT_DIR="clients/${CLIENT_NAME// /_}_${DATE}"

mkdir -p "$CLIENT_DIR"/{audit,agent,onboarding,automation}

echo "=== Onboarding: $CLIENT_NAME ==="

# Step 1: Website Audit (if applicable)
echo "Step 1: Running website audit..."
website=$(grep -i "website" "$CLIENT_FILE" | cut -d: -f2 | xargs)
if [[ -n "$website" ]]; then
    echo "$website" | fabric -p audit_business_website > "$CLIENT_DIR/audit/website_audit.txt"
    echo "✓ Audit complete: $CLIENT_DIR/audit/website_audit.txt"
fi

# Step 2: Lead Guardian Design
echo "Step 2: Designing Lead Guardian agent..."
cat "$CLIENT_FILE" | fabric -p create_lead_guardian > "$CLIENT_DIR/agent/lead_guardian.txt"
echo "✓ Agent designed: $CLIENT_DIR/agent/lead_guardian.txt"

# Step 3: Onboarding Journey
echo "Step 3: Creating onboarding journey..."
cat "$CLIENT_FILE" | fabric -p setup_customer_onboarding > "$CLIENT_DIR/onboarding/journey.txt"
echo "✓ Journey mapped: $CLIENT_DIR/onboarding/journey.txt"

# Step 4: Automation Scripts
echo "Step 4: Generating automation scripts..."
echo "Create automation scripts for $CLIENT_NAME based on their needs:
$(cat $CLIENT_FILE)" | fabric -p automate_task > "$CLIENT_DIR/automation/scripts.txt"
echo "✓ Scripts generated: $CLIENT_DIR/automation/scripts.txt"

echo ""
echo "=== ONBOARDING COMPLETE ==="
echo "All deliverables in: $CLIENT_DIR/"
tree "$CLIENT_DIR/"
```

---

## Lead Magnet to Funnel Pipeline

### Overview

```
generate_lead_magnet → build_sales_funnel → create_outbound_sequence → setup_customer_onboarding
```

### Complete Funnel Build Script

```bash
#!/bin/bash
# Lead Magnet to Funnel Pipeline
# Usage: ./build_funnel.sh audience_profile.txt

AUDIENCE_FILE=$1
DATE=$(date +%Y-%m-%d)
FUNNEL_DIR="funnel_${DATE}"

mkdir -p "$FUNNEL_DIR"/{lead_magnet,funnel,sequences,onboarding}

echo "=== Building Complete Sales Funnel ==="

# Step 1: Create Lead Magnet
echo "Step 1: Designing lead magnet..."
cat "$AUDIENCE_FILE" | fabric -p generate_lead_magnet > "$FUNNEL_DIR/lead_magnet/design.txt"

# Step 2: Build Full Funnel
echo "Step 2: Designing sales funnel..."
cat "$AUDIENCE_FILE" | fabric -p build_sales_funnel > "$FUNNEL_DIR/funnel/design.txt"

# Step 3: Create Outbound Sequences
echo "Step 3: Creating outbound sequences..."
cat "$FUNNEL_DIR/funnel/design.txt" | fabric -p create_outbound_sequence > "$FUNNEL_DIR/sequences/outbound.txt"

# Step 4: Design Post-Sale Onboarding
echo "Step 4: Designing customer onboarding..."
cat "$FUNNEL_DIR/funnel/design.txt" | fabric -p setup_customer_onboarding > "$FUNNEL_DIR/onboarding/journey.txt"

echo ""
echo "=== FUNNEL BUILD COMPLETE ==="
echo ""
echo "Deliverables:"
echo "1. Lead Magnet: $FUNNEL_DIR/lead_magnet/design.txt"
echo "2. Funnel Design: $FUNNEL_DIR/funnel/design.txt"
echo "3. Outbound Sequences: $FUNNEL_DIR/sequences/outbound.txt"
echo "4. Onboarding Journey: $FUNNEL_DIR/onboarding/journey.txt"
```

---

## Business Launch Workflow

### Overview

```
create_monetization_plan → build_financial_model → optimize_pricing_strategy → automate_business_plan → create_crm_workflow
```

### Business Launch Script

```bash
#!/bin/bash
# Business Launch Workflow
# Usage: ./launch_business.sh business_assets.txt

ASSETS_FILE=$1
DATE=$(date +%Y-%m-%d)
LAUNCH_DIR="business_launch_${DATE}"

mkdir -p "$LAUNCH_DIR"/{monetization,financials,pricing,operations,crm}

echo "=== BUSINESS LAUNCH WORKFLOW ==="

# Step 1: Create Monetization Plan
echo "Step 1: Creating monetization roadmap..."
cat "$ASSETS_FILE" | fabric -p create_monetization_plan > "$LAUNCH_DIR/monetization/plan.txt"

# Step 2: Build Financial Model
echo "Step 2: Building financial projections..."
cat "$LAUNCH_DIR/monetization/plan.txt" | fabric -p build_financial_model > "$LAUNCH_DIR/financials/model.txt"

# Step 3: Optimize Pricing
echo "Step 3: Designing pricing strategy..."
cat "$LAUNCH_DIR/monetization/plan.txt" | fabric -p optimize_pricing_strategy > "$LAUNCH_DIR/pricing/strategy.txt"

# Step 4: Create Operations Blueprint
echo "Step 4: Creating operations automation..."
cat "$LAUNCH_DIR/monetization/plan.txt" | fabric -p automate_business_plan > "$LAUNCH_DIR/operations/blueprint.txt"

# Step 5: Design CRM Workflows
echo "Step 5: Designing CRM automation..."
cat "$LAUNCH_DIR/operations/blueprint.txt" | fabric -p create_crm_workflow > "$LAUNCH_DIR/crm/workflows.txt"

echo ""
echo "=== BUSINESS LAUNCH PLAN COMPLETE ==="
echo ""
echo "Review order:"
echo "1. Monetization Plan: $LAUNCH_DIR/monetization/plan.txt"
echo "2. Financial Model: $LAUNCH_DIR/financials/model.txt"
echo "3. Pricing Strategy: $LAUNCH_DIR/pricing/strategy.txt"
echo "4. Operations Blueprint: $LAUNCH_DIR/operations/blueprint.txt"
echo "5. CRM Workflows: $LAUNCH_DIR/crm/workflows.txt"
```

---

## Revenue Optimization Pipeline

### Overview

```
audit_business_website → analyze_business_gaps → build_sales_funnel → optimize_pricing_strategy → build_financial_model
```

### Revenue Optimization Script

```bash
#!/bin/bash
# Revenue Optimization Pipeline
# Usage: ./optimize_revenue.sh website_url

WEBSITE=$1
DATE=$(date +%Y-%m-%d)
OPT_DIR="revenue_optimization_${DATE}"

mkdir -p "$OPT_DIR"/{audit,gaps,funnel,pricing,forecast}

echo "=== REVENUE OPTIMIZATION PIPELINE ==="

# Step 1: Audit Current State
echo "Step 1: Auditing current website..."
echo "$WEBSITE" | fabric -p audit_business_website > "$OPT_DIR/audit/current_state.txt"

# Step 2: Identify Gaps
echo "Step 2: Analyzing revenue gaps..."
cat "$OPT_DIR/audit/current_state.txt" | fabric -p analyze_business_gaps > "$OPT_DIR/gaps/analysis.txt"

# Step 3: Redesign Funnel
echo "Step 3: Redesigning sales funnel..."
cat "$OPT_DIR/gaps/analysis.txt" | fabric -p build_sales_funnel > "$OPT_DIR/funnel/optimized.txt"

# Step 4: Optimize Pricing
echo "Step 4: Optimizing pricing strategy..."
cat "$OPT_DIR/funnel/optimized.txt" | fabric -p optimize_pricing_strategy > "$OPT_DIR/pricing/optimized.txt"

# Step 5: Forecast Impact
echo "Step 5: Forecasting revenue impact..."
cat "$OPT_DIR/pricing/optimized.txt" | fabric -p build_financial_model > "$OPT_DIR/forecast/projections.txt"

echo ""
echo "=== OPTIMIZATION COMPLETE ==="
echo ""
echo "Expected improvements identified in:"
echo "- Audit: $OPT_DIR/audit/current_state.txt"
echo "- Gaps: $OPT_DIR/gaps/analysis.txt"
echo "- Funnel: $OPT_DIR/funnel/optimized.txt"
echo "- Pricing: $OPT_DIR/pricing/optimized.txt"
echo "- Forecast: $OPT_DIR/forecast/projections.txt"
```

---

## Automation Scripts

### Daily Prospecting Automation

```bash
#!/bin/bash
# daily_prospecting.sh - Run daily at 8am
# Add to crontab: 0 8 * * 1-5 /path/to/daily_prospecting.sh

VERTICALS=("plumbers" "electricians" "dentists" "lawyers")
LOCATIONS=("Austin TX" "Dallas TX" "Houston TX")
DATE=$(date +%Y-%m-%d)

for vertical in "${VERTICALS[@]}"; do
    for location in "${LOCATIONS[@]}"; do
        echo "Prospecting: $vertical in $location"

        echo "Find $vertical in $location without online booking" | \
          fabric -p scrape_local_businesses > \
          "prospects/${DATE}_${vertical}_${location// /_}.txt"
    done
done

echo "Daily prospecting complete: $(date)"
```

### Batch Email Processing

```bash
#!/bin/bash
# batch_email_creator.sh
# Usage: ./batch_email_creator.sh prospects_file.txt

PROSPECTS=$1
OUTPUT_DIR="emails_$(date +%Y-%m-%d)"
mkdir -p "$OUTPUT_DIR"

# Process each prospect
while IFS= read -r prospect; do
    # Skip empty lines
    [[ -z "$prospect" ]] && continue

    # Create safe filename
    filename=$(echo "$prospect" | tr ' ' '_' | tr -cd '[:alnum:]_')

    echo "Processing: $prospect"

    # Chain: gaps → personalize → email
    echo "$prospect" | fabric -p analyze_business_gaps | \
      fabric -p personalize_from_gaps | \
      fabric -p draft_cold_email > "$OUTPUT_DIR/${filename}.txt"

done < "$PROSPECTS"

echo "Batch complete! Emails in: $OUTPUT_DIR/"
```

### Weekly Pipeline Report

```bash
#!/bin/bash
# weekly_pipeline.sh - Generate weekly pipeline status
# Run: Fridays at 5pm

DATE=$(date +%Y-%m-%d)
REPORT_DIR="reports"
mkdir -p "$REPORT_DIR"

# Gather metrics from CRM exports (adjust paths)
cat crm_export.csv | fabric -p build_financial_model > "$REPORT_DIR/forecast_${DATE}.txt"

# Analyze conversion issues
cat failed_deals.txt | fabric -p analyze_business_gaps > "$REPORT_DIR/loss_analysis_${DATE}.txt"

# Create pricing review
cat current_deals.txt | fabric -p optimize_pricing_strategy > "$REPORT_DIR/pricing_review_${DATE}.txt"

echo "Weekly pipeline report generated: $REPORT_DIR/"
```

---

## Advanced Multi-Pattern Workflows

### The "Zero to Revenue" Workflow

For bootstrapping a new service business:

```bash
#!/bin/bash
# zero_to_revenue.sh
# Complete workflow from idea to first client

# Phase 1: Business Design
echo "=== PHASE 1: BUSINESS DESIGN ==="
cat your_assets.txt | fabric -p create_monetization_plan > phase1_monetization.txt
cat phase1_monetization.txt | fabric -p optimize_pricing_strategy > phase1_pricing.txt
cat phase1_pricing.txt | fabric -p build_financial_model > phase1_forecast.txt

# Phase 2: Lead Magnet & Funnel
echo "=== PHASE 2: FUNNEL DESIGN ==="
cat target_audience.txt | fabric -p generate_lead_magnet > phase2_lead_magnet.txt
cat target_audience.txt | fabric -p build_sales_funnel > phase2_funnel.txt

# Phase 3: Prospecting & Outreach
echo "=== PHASE 3: FIRST PROSPECTS ==="
echo "Find [your vertical] in [your city] without [your service]" | \
  fabric -p scrape_local_businesses > phase3_prospects.txt
cat phase3_prospects.txt | fabric -p analyze_business_gaps > phase3_gaps.txt
cat phase3_gaps.txt | fabric -p personalize_from_gaps > phase3_copy.txt
cat phase3_copy.txt | fabric -p draft_cold_email > phase3_emails.txt
cat phase3_emails.txt | fabric -p draft_followup_sequence > phase3_sequences.txt

# Phase 4: Sales Infrastructure
echo "=== PHASE 4: SALES INFRASTRUCTURE ==="
cat phase2_funnel.txt | fabric -p create_crm_workflow > phase4_crm.txt
cat phase2_funnel.txt | fabric -p automate_lead_enrichment > phase4_enrichment.txt

echo ""
echo "=== ZERO TO REVENUE COMPLETE ==="
echo "You now have:"
echo "1. Business model and pricing"
echo "2. Lead magnet and funnel"
echo "3. 50+ prospects with personalized emails"
echo "4. CRM and automation setup"
echo ""
echo "Next: Send emails, handle responses, close deals!"
```

### The "Client Rescue" Workflow

For taking over a struggling client:

```bash
#!/bin/bash
# client_rescue.sh
# Complete rescue workflow for underperforming client

CLIENT=$1
RESCUE_DIR="rescue_${CLIENT}_$(date +%Y-%m-%d)"
mkdir -p "$RESCUE_DIR"

# Diagnose
echo "=== DIAGNOSIS ==="
echo "$CLIENT website" | fabric -p audit_business_website > "$RESCUE_DIR/01_audit.txt"
cat "$RESCUE_DIR/01_audit.txt" | fabric -p analyze_business_gaps > "$RESCUE_DIR/02_gaps.txt"

# Prescribe
echo "=== PRESCRIPTION ==="
cat "$RESCUE_DIR/02_gaps.txt" | fabric -p build_sales_funnel > "$RESCUE_DIR/03_funnel.txt"
cat "$RESCUE_DIR/03_funnel.txt" | fabric -p optimize_pricing_strategy > "$RESCUE_DIR/04_pricing.txt"

# Automate
echo "=== AUTOMATION ==="
cat "$RESCUE_DIR/04_pricing.txt" | fabric -p automate_business_plan > "$RESCUE_DIR/05_automation.txt"
cat client_details.txt | fabric -p create_lead_guardian > "$RESCUE_DIR/06_agent.txt"
cat "$RESCUE_DIR/05_automation.txt" | fabric -p create_crm_workflow > "$RESCUE_DIR/07_crm.txt"

# Project
echo "=== PROJECTION ==="
cat "$RESCUE_DIR/04_pricing.txt" | fabric -p build_financial_model > "$RESCUE_DIR/08_forecast.txt"

echo ""
echo "=== RESCUE PLAN COMPLETE ==="
echo "Present to client: $RESCUE_DIR/08_forecast.txt"
```

### The "Vertical Domination" Workflow

For owning a specific vertical:

```bash
#!/bin/bash
# vertical_domination.sh
# Systematic approach to dominating a vertical

VERTICAL=$1  # e.g., "plumbers"
REGIONS=("Austin TX" "Dallas TX" "Houston TX" "San Antonio TX")
DOM_DIR="domination_${VERTICAL}_$(date +%Y-%m-%d)"

mkdir -p "$DOM_DIR"/{prospects,analysis,campaigns,sequences}

# Prospect all regions
echo "=== PROSPECTING ALL REGIONS ==="
for region in "${REGIONS[@]}"; do
    safe_region=$(echo "$region" | tr ' ' '_')

    echo "Find $VERTICAL in $region without online booking" | \
      fabric -p scrape_local_businesses > "$DOM_DIR/prospects/${safe_region}.txt"
done

# Combine and analyze
echo "=== ANALYZING ==="
cat "$DOM_DIR/prospects/"*.txt | fabric -p analyze_business_gaps > "$DOM_DIR/analysis/combined_gaps.txt"

# Create campaigns
echo "=== CREATING CAMPAIGNS ==="
cat "$DOM_DIR/analysis/combined_gaps.txt" | fabric -p personalize_from_gaps > "$DOM_DIR/campaigns/copy_kit.txt"
cat "$DOM_DIR/campaigns/copy_kit.txt" | fabric -p draft_cold_email > "$DOM_DIR/campaigns/emails.txt"
cat "$DOM_DIR/campaigns/emails.txt" | fabric -p draft_followup_sequence > "$DOM_DIR/sequences/full_sequence.txt"

# Build vertical-specific funnel
echo "=== BUILDING FUNNEL ==="
echo "Audience: $VERTICAL business owners
Pain points: No online booking, missed calls, lost leads" | \
  fabric -p generate_lead_magnet > "$DOM_DIR/lead_magnet.txt"

echo "Target: $VERTICAL businesses
Goal: 20 new clients this quarter" | \
  fabric -p build_sales_funnel > "$DOM_DIR/funnel.txt"

echo ""
echo "=== VERTICAL DOMINATION PLAN COMPLETE ==="
echo "Prospects across ${#REGIONS[@]} regions"
echo "Ready for systematic outreach"
```

---

## Quick Reference: Common Chains

| Goal | Chain |
|------|-------|
| Find & email prospects | `scrape_local_businesses → analyze_business_gaps → personalize_from_gaps → draft_cold_email` |
| Process inbox | `classify_email_reply → flag_hot_lead → draft_reply` |
| Close deals | `qualify_leads → create_winning_proposal` |
| Onboard clients | `audit_business_website → create_lead_guardian → setup_customer_onboarding` |
| Build funnel | `generate_lead_magnet → build_sales_funnel → create_outbound_sequence` |
| Launch business | `create_monetization_plan → optimize_pricing_strategy → build_financial_model` |
| Automate operations | `automate_business_plan → create_crm_workflow → automate_task` |
| Optimize revenue | `audit_business_website → analyze_business_gaps → optimize_pricing_strategy` |

---

## Tips for Effective Chaining

1. **Start simple** - Master 2-3 pattern chains before building complex workflows
2. **Save intermediates** - Always save each step's output for debugging
3. **Iterate** - Review and refine outputs at each step before continuing
4. **Batch process** - Run similar operations together for efficiency
5. **Automate gradually** - Start manual, then script what works
6. **Monitor quality** - Spot-check outputs to ensure pattern chain is working
7. **Version control** - Keep scripts in git for iteration tracking

---

## Next Steps

1. **Start with prospecting chain** - Most immediate ROI
2. **Add inbox automation** - Handle responses efficiently
3. **Build closing chain** - Convert opportunities
4. **Scale with automation** - Script repeatable workflows

See [BUSINESS_PATTERNS_USAGE_GUIDE.md](./BUSINESS_PATTERNS_USAGE_GUIDE.md) for individual pattern details.

See [BUSINESS_OPERATIONS_DAILY_GUIDE.md](./BUSINESS_OPERATIONS_DAILY_GUIDE.md) for daily workflow integration.
