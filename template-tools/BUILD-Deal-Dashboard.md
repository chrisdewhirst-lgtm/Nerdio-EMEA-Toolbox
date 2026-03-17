# BUILD: Deal Dashboard Tool

## Purpose
Pipeline tracking dashboard that visualizes all deals by stage, shows ARR estimates, close dates, and progression velocity. At-a-glance view of your entire pipeline health and forecast accuracy.

## What This Tool Does
- **Pipeline Stage View**: See all deals organized by stage with visual flow
- **ARR Forecasting**: Calculate total pipeline value, weighted by probability, and forecast by month
- **Close Date Timeline**: Visual calendar showing when deals are expected to close
- **Deal Progression**: Track how long deals have been in each stage
- **Stage Velocity**: See average time deals spend in each stage to forecast closure
- **Forecast Accuracy**: Compare forecast vs. actual for recently closed deals
- **Territory Overview**: Summary metrics for your territory (total pipeline, monthly forecast, win rate)
- **Deal Health Tracking**: Visual indicators of which deals are progressing normally vs. stuck

## Data You Need to Provide

### 1. Deal List (CSV format)
- Deal Name
- Account Name
- Deal Value (in EUR or your local currency)
- Pipeline Stage (Discovery, Qualification, Proposal, Negotiation, Closed Won, Closed Lost)
- Close Date (expected, in YYYY-MM-DD format)
- Owner
- Days in Current Stage
- Last Activity Date
- Probability % (if using weighted forecast)

### 2. Historical Closed Deals (optional but recommended)
- Deal Name
- Account Name
- Deal Value
- Original Close Date (forecast)
- Actual Close Date
- Stage history (which stages and how long in each)

**Example CSV format:**
```
Deal Name,Account Name,Value,Stage,Close Date,Owner,Days in Stage,Last Activity,Probability
Acme DaaS Migration,Acme Corp,250000,Proposal,2026-05-15,John Smith,14,2026-03-15,80
TechStart VDI,TechStart Ltd,85000,Qualification,2026-06-30,Jane Doe,21,2026-03-10,50
Global Finance RDS,Global Finance Inc,180000,Negotiation,2026-04-30,John Smith,7,2026-03-16,90
```

## Prompt for Claude

Copy and paste this prompt into Claude, replacing the bracketed sections with your data:

---

**I need you to create a Deal Dashboard Tool for my Nerdio pipeline.**

Please build a single-file HTML application with all CSS and JavaScript embedded that includes:

**Core Features:**
1. **Data Import**:
   - Upload CSV with deal pipeline data
   - Parse deal value, stage, close dates, and owner
   - Calculate derived metrics (days in stage, stage progression time)
   - Import historical closed deals for accuracy tracking

2. **Pipeline Stage View** (Kanban-style):
   - Visual columns for each stage: Discovery, Qualification, Proposal, Negotiation, Closed Won, Closed Lost
   - Show each deal as a card in its respective stage with:
     - Deal name and account name
     - Deal value
     - Close date (expected)
     - Owner name
     - Days in current stage
     - Health indicator (RAG status based on days in stage vs. average)
   - Sort deals within each stage by close date (soonest first)
   - Drag-and-drop to move deals between stages (optional interactive feature)
   - Click deal card to see full details

3. **Territory Summary Dashboard** (top of page):
   - Total pipeline value (sum of all open deals)
   - Weighted forecast (value × probability %) for realistic forecast
   - Number of deals in each stage (distribution)
   - Close dates breakdown: Due this month, next month, future months
   - Average deal size
   - Win rate % (closed won / closed won + lost, if historical data available)
   - Key metric cards with visual indicators

4. **Monthly Forecast View**:
   - Calendar-style view showing expected close dates
   - Aggregate deal value by month
   - Month-over-month forecast (Q2 forecast, Q3 forecast, etc.)
   - Color-coded intensity by deal value in each month
   - Probability-weighted forecast vs. base forecast comparison
   - Highlight months that meet/exceed/fall short of targets

5. **Deal Timeline** (visual):
   - Horizontal timeline showing all deals by close date
   - X-axis: Calendar dates (current month through +6 months)
   - Y-axis: Deal value or owner
   - Bubbles/bars for each deal positioned by close date
   - Color by stage or health status
   - Hover to see deal details
   - Zoom to specific date range

6. **Stage Progression Analysis**:
   - For each stage, show:
     - Number of deals
     - Total value in stage
     - Average days deals spend in this stage (based on historical data)
     - Velocity: How many deals typically move through this stage per month
     - Expected exit dates based on velocity
   - Highlight stages where deals are getting stuck (slower velocity)

7. **Deal Health Tracking**:
   - Compare "Days in Stage" vs. "Average Days in Stage" for that stage
   - Green: Deal is progressing on normal timeline
   - Amber: Deal is slower than average (44% slower; alert to check on it)
   - Red: Deal is significantly behind (60%+ slower; at risk of slipping)
   - Show recommended actions for slow-moving deals (follow up, check-in, escalate)

8. **Close Date Risk Analysis**:
   - Deals at risk of missing their close date:
     - Current stage duration + average remaining stage durations > days until close date = risk
   - Red flag deals that are unlikely to close on their forecasted date
   - Suggest revised close dates based on actual velocity
   - Alert when multiple large deals are at risk of missing same month target

9. **Owner/Rep Performance**:
   - Summary cards per sales rep showing:
     - Total pipeline value owned
     - Number of deals
     - Average deal size
     - Deals closing this month (next milestone)
     - Pipeline coverage ratio (pipeline / quota, if you provide quota data)

10. **Forecast Accuracy** (if historical data provided):
    - Compare closed deals: Original close date vs. actual close date
    - Calculate forecast accuracy % (deals closed within 10 days of forecast)
    - Show slippage patterns (tends to close early/late?)
    - Use this to adjust current forecasts

11. **Deal Drill-Down**:
    - Click any deal to see full details:
      - Account info, value, probability, close date
      - Deal history: stage progression, time in each stage
      - Owner, primary contact, description
      - Recent activities and next steps
      - Risk factors and health assessment
      - Recommended actions to keep deal on track

12. **Reporting & Export**:
    - Export pipeline summary (HTML report with stage breakdown, forecast by month, team summary)
    - Export deal list with current stage, close date, value (CSV)
    - Generate forecast report (monthly/quarterly revenue forecast)
    - Email-friendly summary view

**Visual Design**:
- Use Nerdio brand colors: Navy (#0B1B3D) for headers, Teal (#00B4D8) for deal cards, Green (#00C48C) for on-track deals, Yellow (#FFA500) for at-risk, Red (#FF6B6B) for critical
- Kanban board layout familiar to sales teams
- Cards show key info at a glance: deal name, value, close date, owner
- Timeline visualization clear and easy to scan
- Charts for pipeline distribution and forecast
- Responsive design for desktop viewing and team display screens
- Print-friendly summary reports

**Data Handling**:
- Parse CSV deal imports
- Calculate metrics in browser (no external API)
- Store session data in browser memory
- Allow data re-upload to refresh
- Validate deal values and dates
- Handle missing probability data gracefully (default to 50%)

---

## Tips for Success
1. **Weekly Updates**: Refresh your deal list weekly from your CRM to keep dashboard current
2. **Probability Realistic**: Use probability scores that reflect actual deal health (not wishful thinking)
3. **Close Dates Honest**: Use realistic close dates; adjust when deals slip to improve forecast accuracy
4. **Stage Durations**: Use historical data to inform stage progression expectations
5. **Owner Accountability**: Review deal dashboard with reps weekly; identify which deals need action
6. **Forecast Monthly**: Use this dashboard to build accurate monthly revenue forecasts

## Pipeline Health Indicators
- **Green Zone**: Deals progressing on schedule, closing on forecast date, healthy probability
- **Yellow Zone**: Deals moving slowly, close date may slip, probability declining
- **Red Zone**: Deals significantly behind schedule, at risk of missing close date or no-decision

## Common Issues to Watch For
- **Discovery Pileup**: Too many deals stuck in early stages with unclear probability
- **Proposal Stall**: Deals spending too long in proposal without moving to negotiation
- **Month-End Cliff**: Too many deals closing in last week of month (indicates poor distribution)
- **False Forecast**: Including low-probability deals in monthly forecast inflates unrealistic expectations

## Next Steps
- Generate your personalized Deal Dashboard using the prompt above
- Export your current deal pipeline from your CRM as CSV
- Upload pipeline data to initialize your dashboard
- Review pipeline dashboard weekly with your team
- Update close dates and stages as deals progress
- Use forecast view to build monthly revenue targets
- Compare forecast vs. actual monthly to improve prediction accuracy
