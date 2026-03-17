# BUILD: Qualification Scorecard Tool

## Purpose
MEDDPICC (Metrics, Economic Buyer, Decision Criteria, Decision Process, Pain, Identification of Pain, Champion, Competitor) assessment framework for every deal with automated scoring, RAG flags, and deal health percentage.

## What This Tool Does
- **MEDDPICC Assessment**: Score each deal against all 8 MEDDPICC criteria
- **Deal Health Scoring**: Overall health percentage based on how well criteria are met
- **RAG Status Flags**: Red/Amber/Green indicators for each criterion and overall deal
- **Risk Identification**: Highlight missing or weak criteria that could derail the deal
- **Deal Prioritization**: Rank deals by qualification strength within your pipeline
- **Action Items**: Generate specific next steps to strengthen weak criteria
- **Deal Progression Tracking**: Monitor MEDDPICC scores over time as deals progress
- **Sales Team Alignment**: Ensure everyone assesses deals using the same framework

## Data You Need to Provide

### 1. Deal Pipeline (CSV format)
- Account Name
- Deal Name
- Deal Value
- Pipeline Stage (Discovery, Qualification, Proposal, Negotiation, Closed Won/Lost)
- Close Date (expected)
- Owner
- Primary Contact
- Competitor (if known)

### 2. Deal Details/Context (via conversation)
Provide for each significant deal:
- Account background
- Current pain points
- Known stakeholders and their roles
- Budget information (if available)
- Timeline/timeline driver
- Competitive situation
- Customer success stories/references

**Example CSV format:**
```
Account Name,Deal Name,Value,Stage,Close Date,Owner,Contact,Competitor
Acme Corp,Acme DaaS Migration,250000,Proposal,2026-05-15,John Smith,Sarah Johnson,Citrix
TechStart Ltd,TechStart VDI,85000,Qualification,2026-06-30,Jane Doe,James Wilson,
```

## Prompt for Claude

Copy and paste this prompt into Claude, replacing the bracketed sections with your data:

---

**I need you to create a Qualification Scorecard Tool using MEDDPICC framework for my Nerdio territory.**

Please build a single-file HTML application with all CSS and JavaScript embedded that includes:

**Core Features:**
1. **Data Import**:
   - Upload CSV with deal pipeline (Account, Deal Name, Value, Stage, Close Date, Owner, Primary Contact, Competitor)
   - Create deal assessment database
   - Link deals to accounts

2. **MEDDPICC Assessment Interface**:
   - For each deal, assess all 8 criteria:
     1. **Metrics**: Have you identified business metrics that matter to them? (e.g., productivity %, uptime, cost savings)
     2. **Economic Buyer**: Have you identified the economic buyer? Do you have sponsor-level access?
     3. **Decision Criteria**: Do you understand their evaluation criteria? Have you influenced them?
     4. **Decision Process**: Do you know the buying process, timeline, and approvals needed?
     5. **Pain**: Have you identified their primary pain/problem? Specific business impact?
     6. **Identification of Pain**: Did they identify the pain, or did you introduce it?
     7. **Champion**: Do you have a champion who understands the solution and can advocate internally?
     8. **Competitor**: Do you know the competition? Have you positioned against them?

3. **Scoring System**:
   - Each criterion: 0-4 point scale
     - 0: Not addressed
     - 1: Weak evidence
     - 2: Moderate evidence
     - 3: Good evidence
     - 4: Strong evidence / Fully qualified
   - Detailed guidance/tooltip for each criterion to help reps understand scoring
   - Allow multiple scores per criterion over time to track evolution

4. **Deal Health Calculation**:
   - Calculate overall "Deal Health %" based on MEDDPICC scores:
     - Sum of all 8 criterion scores / 32 possible points × 100 = Health %
     - Display as large percentage or thermometer visualization
   - Health thresholds:
     - 80-100%: Deal is well-qualified, high confidence to close
     - 60-79%: Deal is qualified, some risks present
     - 40-59%: Deal needs work, significant gaps in qualification
     - 0-39%: Deal is poorly qualified, substantial risk of loss or no-decision

5. **RAG Status Indicators**:
   - Each criterion shows RAG color:
     - Green (3-4 points): Well-qualified
     - Amber (2 points): Partially qualified, needs work
     - Red (0-1 points): Not qualified, critical gap
   - Overall deal RAG: Based on worst criterion or Deal Health %
   - Red flags when any criterion scores 0-1

6. **Deal Cards / Summary View**:
   - List all deals in pipeline with:
     - Account name, deal name, value, stage
     - MEDDPICC score (visual bar or percentage)
     - Overall RAG status (color indicator)
     - Deal health %
     - Sorted by stage and health score
   - Click any deal to see full assessment

7. **Deal Deep-Dive Assessment Page**:
   - Full deal profile: account, value, stage, close date, owner, contact
   - Scoring interface for all 8 MEDDPICC criteria:
     - Score input (0-4 scale with radio buttons)
     - Evidence description (text field): "What evidence supports this score?"
     - Supporting details (notes)
   - RAG status for each criterion with visual indicator
   - Overall deal health % prominently displayed
   - Timeline of assessment scores (show how score changed over weeks)

8. **Risk & Gap Analysis**:
   - Highlight all RED criteria: "Deal at risk in [criterion name]"
   - For each red criterion, suggest specific next steps:
     - Metrics: "Schedule metrics discussion with stakeholder"
     - Economic Buyer: "Escalate to VP IT or CFO - identify economic buyer"
     - Decision Criteria: "Request formal evaluation matrix"
     - Decision Process: "Request deal timeline and approval chain"
     - Pain: "Conduct pain discovery session"
     - Identification of Pain: "Shift from problem discovery to customer-identified pain"
     - Champion: "Identify and develop internal champion"
     - Competitor: "Conduct competitive analysis and position accordingly"

9. **Deal Prioritization View**:
   - Pipeline deals sorted by deal value AND deal health
   - Identify "at-risk" deals (high value, low health)
   - Identify "low-hanging fruit" (progressing well, ready to close)
   - Suggest focus areas (which deals need immediate attention?)
   - Show deals by stage with health indicators

10. **Qualification Journey Tracker**:
    - Show how each MEDDPICC score has evolved over time
    - Visual trend: Improving, stable, or declining qualification
    - Help reps see progress and what's working in their approach
    - Identify stalled deals (no improvement in weeks)

11. **Action Item Generation**:
    - Auto-generate next steps based on weak criteria:
      - "Schedule meeting with economic buyer to discuss decision criteria"
      - "Conduct pain discovery call with [contact]"
      - "Prepare competitive positioning document"
    - Allow custom action items
    - Track action completion

12. **Reporting**:
    - Pipeline health summary: % of deals in each health band (80%+, 60-79%, etc.)
    - Average MEDDPICC score by stage (what scores are typical at each stage?)
    - Weakest criteria across all deals (where is the team struggling?)
    - Strongest criteria (where is the team excelling?)

**Visual Design**:
- Use Nerdio brand colors: Navy (#0B1B3D) for headers, Teal (#00B4D8) for inputs, Green (#00C48C) for strong scores, Red (#FF6B6B) for weak scores
- Large, clear RAG indicators (colored circles/squares)
- Deal health visualized as progress bar or thermometer
- Clean form layout for MEDDPICC scoring
- Mobile-responsive for field reps on the go
- Print-friendly deal scorecard

**Data Handling**:
- Store all assessments in browser memory
- Timestamp each assessment
- Allow export of deal pipeline with health scores as CSV
- Validate numeric scores (0-4)
- Preserve assessment history for trend tracking

---

## Tips for Success
1. **Regular Assessment**: Re-score deals weekly as new information emerges
2. **Honest Scoring**: Score objectively - '2' (weak evidence) is better than inflating with false confidence
3. **Focus on Red Items**: When you see red criteria, that's your action list
4. **Team Calibration**: Review scoring as a team to ensure consistency
5. **Early-Stage Deals**: Expect low scores in Discovery - that's normal; focus on closing the gaps
6. **Late-Stage Deals**: Proposal/Negotiation deals should score 3-4 on most criteria

## MEDDPICC Quick Reference
- **Metrics**: Quantifiable business impact (cost %, uptime %, productivity %, headcount efficiency)
- **Economic Buyer**: Person who controls the budget (usually CFO, VP Finance, or VP Ops)
- **Decision Criteria**: The specific evaluation criteria they'll use (performance, cost, integration, support)
- **Decision Process**: Steps, timeline, approvals (RFP, evaluation committee, executive approval)
- **Pain**: Root business problem they're trying to solve (not just "want cloud")
- **Identification of Pain**: Did they discover it internally or did you bring it to them?
- **Champion**: Internal advocate who understands your solution and can sell internally
- **Competitor**: Who else they're evaluating; how do you differentiate?

## Typical MEDDPICC Evolution
- **Discovery stage**: Scores improving as you discover pain and identify stakeholders
- **Qualification stage**: All 8 criteria getting clarity; scores 2-3 is good here
- **Proposal stage**: Should have strong evidence on most criteria (3-4)
- **Negotiation stage**: All criteria should be qualified; dealing with final objections

## Next Steps
- Generate your personalized Qualification Scorecard using the prompt above
- Import your current deal pipeline as CSV
- Start assessing each deal using the MEDDPICC framework
- Focus on turning Red criteria into Amber or Green through specific actions
- Re-assess deals weekly and review progress with your manager
- Use deal health scores to prioritize pipeline activities
