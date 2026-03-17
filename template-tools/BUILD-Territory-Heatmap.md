# BUILD: Territory Heatmap Tool

## Purpose
Creates a visual matrix of your territory colour-coded by account fit score, deal stage, and engagement level. This provides at-a-glance visibility of where deals are, which accounts need attention, and territory coverage.

## What This Tool Does
- **Territory Heatmap Matrix**: Visual grid showing accounts colour-coded by fit score, deal stage, and engagement
- **Multiple View Modes**: Switch between fit-focused, pipeline-focused, and engagement-focused views
- **Account Clustering**: Groups accounts by region, sector, or tier for territorial analysis
- **Pipeline Visualization**: Stacked view showing accounts across deal stages
- **Engagement Tracking**: Color intensity shows recent activity level
- **Performance vs Target**: Compares territory metrics against personal/team targets
- **Territory Planning**: Identify account gaps, overserved regions, and prospecting opportunities

## Data You Need to Provide

### 1. Territory Definitions (CSV format)
Define your territory structure:
- Territory Name/ID
- Country/Region
- Key Cities/Districts
- Target Performance ($ARR target, account targets, deal targets)

**Example:**
```
Territory,Country,Region,ARR Target,Account Target,Deal Target
EMEA-UK-001,United Kingdom,London Southeast,500000,25,12
EMEA-DE-001,Germany,Stuttgart Frankfurt,450000,22,10
```

### 2. Account Allocations (CSV format)
List all accounts in each territory:
- Account Name
- Territory
- Sector/Industry
- Employee Count
- Current ARR
- Account Tier

### 3. Pipeline Data (CSV format)
Current deal pipeline:
- Account Name
- Deal Name
- Deal Value
- Pipeline Stage
- Days in Stage
- Close Date (expected)
- Owner

### 4. Activity Metrics (CSV format or via CRM export)
Recent engagement:
- Account Name
- Last Activity Date
- Activity Type (meeting, email, call, etc.)
- Days Since Last Activity
- Activity Count (last 30/60/90 days)

**Example:**
```
Account Name,Territory,Sector,Employee Count,ARR,Tier,Last Activity,Days Since,Activity Count
Acme Corp,EMEA-UK-001,Manufacturing,2500,150000,Enterprise,2026-03-15,2,8
TechStart Ltd,EMEA-DE-001,Software,180,25000,SMB,2026-02-10,35,1
```

## Prompt for Claude

Copy and paste this prompt into Claude, replacing the bracketed sections with your data:

---

**I need you to create a Territory Heatmap Tool for my Nerdio territory.**

Please build a single-file HTML application with all CSS and JavaScript embedded that includes:

**Core Features:**
1. **Data Import**:
   - Upload CSV files with account allocations, pipeline data, and activity metrics
   - Define territory targets (ARR goal, account count, deal count)
   - Parse and validate all imported data

2. **Heatmap Matrix Views** (user can switch between):
   - **Fit Score View**: Accounts color-coded by ICP fit score (Green >75%, Amber 50-74%, Red <50%)
   - **Pipeline Stage View**: Accounts grouped by deal stage (Discovery, Qualification, Proposal, Negotiation, Closed)
   - **Engagement Heatmap**: Accounts color-coded by recency of activity (Green: <7 days, Yellow: 8-30 days, Red: 30+ days with no activity)
   - **Territory Overview**: Accounts clustered by territory/region

3. **Account Positioning Matrix**:
   - X-axis: Account Fit Score or ARR (user selectable)
   - Y-axis: Pipeline Stage or Days Since Last Activity
   - Bubble size: Deal value or ARR
   - Color: Fit score or engagement level
   - Click any bubble to drill into account details

4. **Territory Performance Dashboard**:
   - Current performance vs target for each territory:
     - ARR achieved / ARR target (progress bar)
     - Accounts managed / account target
     - Active deals / deal target
   - Visual RAG status for each territory (Green/Amber/Red based on achievement %)
   - Comparison of actual vs planned metrics

5. **Account Status Cards** (in heatmap):
   - Account name, tier, sector, current ARR
   - Fit score and pipeline stage
   - Last activity date and type
   - Active deal count and total pipeline value
   - Next action recommendation
   - Color-coded border indicating overall account health

6. **Engagement Heat Analysis**:
   - Show which accounts need attention (no recent activity but high fit)
   - Identify over-managed accounts (excessive activity on low-fit accounts)
   - Highlight good engagement patterns (frequent touchpoints with high-fit accounts)
   - Recommend account prioritization based on fit × engagement opportunity

7. **Filters & Sorting**:
   - Filter by territory, sector, account tier, fit band, pipeline stage
   - Sort by various criteria (ARR, fit score, last activity, deal count)
   - Search by account name
   - Save filter combinations for quick access

**Visual Design**:
- Use Nerdio brand colors: Navy (#0B1B3D) for headers, Teal (#00B4D8) for highlights
- Color intensity for engagement: Green (#00C48C) for active, Yellow (#FFA500) for warming, Red (#FF6B6B) for cold
- Heatmap grid with clear cell separation
- Hover effects showing account details
- Responsive design for desktop viewing

**Data Handling**:
- Parse multiple CSV uploads
- Calculate derived metrics (days since activity, deal pipeline totals, performance %)
- Handle missing data gracefully
- Allow re-upload to refresh data
- Store session data in browser memory

---

## Tips for Success
1. **Update Regularly**: Import fresh activity and pipeline data weekly to keep heatmap current
2. **Territory Targets**: Set realistic targets based on historical performance and territory size
3. **Activity Metrics**: Include all touchpoints (meetings, calls, emails, content sends, demos)
4. **Fit Scoring**: Use fit scores from your ICP Profiler tool for consistent evaluation
5. **Engagement Cadence**: Aim for high-fit accounts to have activity every 7-14 days
6. **Gap Analysis**: Use heatmap to identify under-served sectors or regions

## Common Heatmap Patterns
- **Green hot spots**: High-fit, active accounts - nurture these carefully
- **Yellow warm spots**: Good fit, some activity - increase engagement cadence
- **Red cold spots**: High fit, no activity - immediate outreach needed
- **Low-engagement gray areas**: Identify if due to low fit (okay to deprioritize) or just neglect

## Next Steps
- Generate your personalized Territory Heatmap using the prompt above
- Import your account allocations, pipeline, and activity data
- Review heatmap monthly during territory planning
- Use heatmap to distribute accounts and identify coverage gaps
- Cross-reference with Account Intelligence tool for deeper analysis
