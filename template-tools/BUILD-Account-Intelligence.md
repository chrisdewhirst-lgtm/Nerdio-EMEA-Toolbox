# BUILD: Account Intelligence Tool

## Purpose
Provides territory-wide account ranking, scoring, signal tracking, and deep-dive analysis per account. This tool aggregates multiple data sources to identify high-value targets, track engagement signals, and assess account health.

## What This Tool Does
- **Account Ranking Matrix**: Scores and ranks all territory accounts by opportunity fit, engagement level, and deal velocity
- **Signal Tracking**: Monitors and displays buying intent signals, activity indicators, and engagement trends per account
- **Account Health Dashboard**: Visual indicators (RAG status) for account status, pipeline stage, and engagement level
- **Deep-Dive Analysis**: Individual account cards with full profile, signal timeline, upcoming opportunities, and next actions
- **Territory Overview**: High-level summary metrics across your entire territory

## Data You Need to Provide

### 1. Territory Account List (CSV format)
Export from your CRM with these columns:
- Account Name
- Sector/Industry
- Employee Count
- ARR (Annual Recurring Revenue)
- Current Spend
- RDS CAL Count
- DaaS Spend
- Intune MAU Count
- Buying Intent Score (0-100)
- Pipeline Stage (e.g., Discovery, Qualification, Proposal, Negotiation)
- Account Tier (Enterprise, Mid-Market, SMB)

**Example CSV format:**
```
Account Name,Sector,Employee Count,ARR,Current Spend,RDS CAL,DaaS Spend,Intune MAU,Buying Intent,Pipeline Stage,Account Tier
Acme Corp,Manufacturing,2500,150000,45000,1200,12000,800,75,Proposal,Enterprise
TechStart Ltd,Software,180,25000,8000,150,2000,120,45,Discovery,SMB
```

### 2. WOPR Data (optional but recommended)
- Account name
- Last WOPR date
- Win probability %
- Opp stage
- Expected close date

### 3. MAL Data (optional)
- Account name
- Last engagement date
- Engagement type (email, call, meeting, content)
- Marketing source

## Prompt for Claude

Copy and paste this prompt into Claude, replacing the bracketed sections with your data:

---

**I need you to create an Account Intelligence Tool for my Nerdio territory.**

Please build a single-file HTML application with all CSS and JavaScript embedded that includes:

**Core Features:**
1. **Data Import**: Upload CSV file with account data including Account Name, Sector, Employee Count, ARR, Current Spend, RDS CAL Count, DaaS Spend, Intune MAU Count, Buying Intent Score (0-100), Pipeline Stage, and Account Tier
2. **Account Ranking**: Automatically score and rank accounts using a weighted formula:
   - ARR & Current Spend (30% weight)
   - Employee Count (20% weight)
   - Buying Intent Score (25% weight)
   - Pipeline Stage progression (15% weight)
   - Engagement signals (10% weight)
3. **Territory Overview Dashboard**:
   - Total accounts, total ARR, average deal size, pipeline value
   - Account distribution by tier and sector
   - Buying intent score distribution chart
4. **Account Ranking Table**: Sortable columns showing each account with rank, score, tier, sector, ARR, buying intent, pipeline stage, and opportunity flag
5. **Account Deep-Dive Cards**: Click any account to see:
   - Full profile (sector, size, ARR, spend breakdown)
   - Current solutions in use (RDS CAL, DaaS, Intune adoption)
   - Buying intent signals and trend
   - Pipeline opportunities
   - Recommended next actions based on fit score and pipeline stage
6. **Signal Tracking**: Visual indicators showing:
   - High buying intent accounts (buying intent score > 70)
   - Accounts ready for engagement (low current spend + high fit score)
   - Stalled accounts needing re-engagement
7. **Filter & Search**: Allow filtering by sector, account tier, pipeline stage, and buying intent threshold

**Visual Design:**
- Use Nerdio brand colors: Navy (#0B1B3D) for headers, Teal (#00B4D8) for highlights, Green (#00C48C) for positive signals, White (#FFFFFF) for backgrounds
- Use RAG status indicators: Green for high-fit/high-intent, Amber for mid-fit, Red for low-intent/stalled
- Clean, modern interface with clear data hierarchy
- Responsive design that works on desktop and tablet

**Data Handling:**
- Parse CSV file uploads
- Store data in browser memory during session
- No external API calls required
- Show data validation errors clearly

---

## Tips for Success
1. **Data Quality**: Ensure all numeric fields (ARR, Employee Count, Buying Intent Score) are properly formatted as numbers
2. **Pipeline Stages**: Use consistent pipeline stage naming (Discovery, Qualification, Proposal, Negotiation, Closed Won)
3. **Account Tiers**: Keep tier naming consistent (Enterprise, Mid-Market, SMB)
4. **Buying Intent Scores**: 0-100 scale where 70+ indicates strong buying signals
5. **Export Regularly**: Save your account intelligence insights to reference during territory planning

## Next Steps
- Generate your personalized Account Intelligence tool using the prompt above
- Upload your territory account data as CSV
- Use the deep-dive analysis to prepare for account-specific meetings
- Cross-reference high-opportunity accounts with your CRM pipeline
