# BUILD: Command Centre Tool

## Purpose
Master dashboard that ties all 9 Nerdio EMEA Toolbox tools together with a unified data upload hub, quick-access launcher, and territory performance dashboard. Single entry point for all your sales operations tools.

## What This Tool Does
- **Master Data Hub**: Central upload point for all your territory data (accounts, pipeline, contacts, activities)
- **Tool Launcher**: Quick-access buttons to all 9 tools with pre-populated data
- **Territory Dashboard**: Key metrics and KPIs at a glance (pipeline value, deals closing this month, account stats)
- **Data Management**: View uploaded data, refresh exports, validate data quality
- **Quick Navigation**: Jump between tools without re-importing data
- **Performance Tracking**: Monitor your territory metrics (ARR, deals, activity)
- **Unified Branding**: All tools accessed through a single, branded interface
- **Setup Wizard**: First-time setup guide to configure territory and import data

## Data You Need to Provide

This tool is the central hub for all your data, so it will use the same data files as the individual tools:

### 1. **Master Account List** (CSV - single source of truth)
- Account Name
- Sector/Industry
- Employee Count
- Location
- ARR/Current Spend
- Account Tier
- Account Owner
- Last Activity Date

### 2. **Contacts & TPID** (CSV)
- Account Name
- Contact Name
- Title / Role
- Department
- Contact Type
- Email

### 3. **Deal Pipeline** (CSV)
- Account Name
- Deal Name
- Deal Value
- Stage
- Close Date
- Owner
- Probability %

### 4. **Activities & Signals** (CSV)
- Account Name
- Activity Type
- Activity Date
- Contact Name (optional)
- Notes

### 5. **Territory Definition** (CSV or form entry)
- Territory Name
- Country/Region
- Target Metrics (ARR goal, account targets, deal targets)

## Prompt for Claude

Copy and paste this prompt into Claude, replacing the bracketed sections with your data:

---

**I need you to create a Command Centre dashboard that ties together all my Nerdio sales tools.**

Please build a single-file HTML application with all CSS and JavaScript embedded that includes:

**Core Features:**

1. **Master Dashboard / Home Screen**:
   - Welcome message with territory name and rep name
   - "Quick Launch" buttons for all 9 tools:
     - Account Intelligence
     - ICP Profiler
     - Territory Heatmap
     - CRM Tracker
     - Meeting Prep
     - Qualification Scorecard
     - Deal Dashboard
     - Reverse Timeline
     - Proposal Builder
   - Each launcher button shows tool icon, name, and brief description
   - Clicking launcher button passes all uploaded data to that tool

2. **Territory Performance Dashboard** (center):
   - **Key Metrics Cards** showing:
     - Pipeline Value (all open deals)
     - Weighted Pipeline Forecast (value × probability %)
     - Number of Accounts in Territory
     - Number of Open Deals
     - Average Deal Size
     - Close Dates this month vs next month
   - **Progress to Target** (if targets defined):
     - ARR achieved / Annual target (progress bar)
     - Accounts managed / Account target
     - Deals closing / Deal target
   - **Recent Activity** (last 5 activities)
   - **Upcoming Milestones** (deals closing in next 30 days, key meetings)

3. **Data Upload Hub** (left sidebar):
   - Central place to import all data files
   - Upload interface for:
     - Account List (CSV)
     - Contacts/TPID (CSV)
     - Deal Pipeline (CSV)
     - Activities & Signals (CSV)
     - Territory Definition (CSV or form)
   - Show file upload status (loaded, validated, errors)
   - Data validation:
     - Check required columns present
     - Check data types (numeric fields are numbers, dates are valid dates)
     - Show warnings about data quality issues
     - Suggest fixes for common errors
   - "Refresh Data" button to re-import updated files
   - Show timestamp of last data import

4. **Data Health Summary**:
   - Account data: X accounts loaded, X with complete info, X missing key data
   - Contact data: X contacts loaded, Y accounts have assigned owners, Z accounts missing primary contact
   - Pipeline data: X deals loaded, Y with close dates, Z at risk (close date < 30 days)
   - Activity data: Last activity date across all accounts, accounts with no activity in 60+ days
   - Data quality score (0-100%) based on completeness

5. **Navigation Menu**:
   - Tool launcher (big buttons for each tool)
   - Settings (territory config, ROI assumptions, sales cycle defaults)
   - Reports (summary reports across tools)
   - Data Management (view/edit uploaded data)
   - Help (quick start guides for each tool)

6. **Settings / Configuration**:
   - Territory Information:
     - Territory name, owner, country/region
     - Target metrics (annual ARR goal, account count goal, deal count goal)
   - Sales Cycle Configuration:
     - Default durations for each stage (Discovery, Qualification, Proposal, Negotiation)
     - Used by Reverse Timeline tool
   - ROI Assumptions (defaults):
     - Infrastructure cost savings %
     - IT staff productivity improvement %
     - Help desk ticket reduction %
     - User productivity improvement %
     - These feed into Proposal Builder
   - Tool Preferences:
     - Currency (EUR, GBP, USD)
     - Date format
     - Color theme (Nerdio branding)

7. **Quick Access / Recent Items**:
   - Recently viewed accounts
   - Recently reviewed deals
   - Recently generated proposals
   - Quick jump back to last tool used

8. **Territory Insights** (analytics):
   - Account distribution by sector (pie chart)
   - Account distribution by tier (bar chart)
   - Pipeline by stage (how many deals in each stage)
   - Pipeline by close date (monthly forecast)
   - Activity heatmap (which accounts need attention?)
   - Buying intent distribution (how many high-intent accounts?)
   - Top 10 accounts by ARR
   - Top 10 accounts by pipeline value

9. **Quick Reports** (exportable):
   - Territory Summary Report: Key metrics, targets, performance
   - Account Intelligence Brief: Top opportunities, signals, next actions
   - Pipeline Forecast: By month and by deal
   - Activity Report: Recent activities, engagement patterns
   - Export as PDF or CSV

10. **Setup Wizard** (first-time user):
    - Step-by-step guide for new reps
    - Step 1: Territory Information (name, location, targets)
    - Step 2: Upload Account List
    - Step 3: Upload Contacts
    - Step 4: Upload Deal Pipeline
    - Step 5: Define Sales Cycle Durations
    - Step 6: Tour of each tool (30-second overview)
    - Completion certificate (congratulations, you're ready!)

11. **Help & Documentation**:
    - "Getting Started" guide
    - FAQ section
    - Troubleshooting tips
    - Video walkthroughs (links to external videos, optional)
    - Quick reference cards for each tool
    - Best practices guide

12. **Data Export & Backup**:
    - Export all uploaded data as CSV or ZIP
    - Import previously exported data to restore
    - Email data backup to self
    - Local browser storage for session persistence

**Visual Design**:
- Use Nerdio brand colors: Navy (#0B1B3D) primary, Teal (#00B4D8) accents, Green (#00C48C) for positive metrics, White (#FFFFFF) backgrounds
- Dashboard-style layout with cards showing metrics and quick actions
- Tool launcher buttons prominent and easy to click (icon + text)
- Navigation menu on left or top
- Clean, professional appearance suitable for daily use
- Responsive design for desktop and tablet
- Status indicators showing which tools have required data

**Data Flow**:
- Store all uploaded CSV data in browser memory
- Pass data between tools seamlessly (user doesn't have to re-upload)
- When user clicks "Account Intelligence" button, pass account + pipeline + activity data to that tool
- Each tool inherits the master data set from Command Centre
- If user uploads new data, all tools automatically have access to updated data

---

## How to Use the Command Centre

### First Time Setup
1. Open Command Centre tool in Claude
2. Complete Setup Wizard (5 minutes)
3. Upload your account list, contacts, pipeline, and activities as CSV files
4. Review data health summary - fix any validation errors
5. Review territory dashboard - see your key metrics

### Daily/Weekly Use
1. Check Territory Dashboard for quick overview
2. Use Tool Launcher buttons to jump into specific tools
3. Data is already loaded - no need to re-import
4. Make updates in individual tools or re-upload refreshed CSVs
5. Data stays synchronized across all tools

### Data Refresh
- Weekly: Download latest account/pipeline data from CRM, upload to Command Centre
- Monthly: Review data quality, archive old data, add new territories if needed
- Tools automatically use latest uploaded data

## Tool Integration Map

```
Command Centre (Master Hub)
├── Account Data → Account Intelligence, ICP Profiler, Territory Heatmap, Meeting Prep
├── Contact Data → CRM Tracker, Meeting Prep
├── Pipeline Data → Deal Dashboard, Qualification Scorecard, Territory Heatmap, Reverse Timeline
├── Activity Data → Territory Heatmap, Meeting Prep, CRM Tracker
├── Territory Config → All tools
└── ROI Assumptions → Proposal Builder
```

## Tips for Success
1. **Single Source of Truth**: Import your account/pipeline data once in Command Centre; all tools use the same data
2. **Weekly Refresh**: Upload fresh pipeline and activity data weekly from your CRM
3. **Data Quality Matters**: Tools are only as good as the data you feed them - keep accounts, contacts, and deals current
4. **Start Simple**: Don't use all 9 tools immediately - pick 2-3 that address your biggest challenges first
5. **Customize Settings**: Configure ROI assumptions and sales cycle durations for your territory
6. **Backup Data**: Export your data monthly as backup

## Common Workflows

### "I have a big opportunity"
1. Open Command Centre
2. Click "Meeting Prep" to generate account brief
3. Click "Reverse Timeline" to plan deal progression
4. Click "Proposal Builder" to create proposal
5. Add to CRM Tracker for activity logging

### "I need to prepare for quarterly business review"
1. Open Command Centre
2. Review Territory Dashboard metrics
3. Generate Territory Summary Report
4. Click "Deal Dashboard" to review pipeline health
5. Click "Account Intelligence" to identify risks and opportunities

### "I want to improve my prospecting"
1. Open Command Centre
2. Click "ICP Profiler" to identify high-fit accounts
3. Click "Territory Heatmap" to find under-served sectors
4. Click "Account Intelligence" to deep-dive on top 20 accounts
5. Create outreach plan based on insights

## Next Steps
- Generate your personalized Command Centre using the prompt above
- Complete the Setup Wizard (first-time users, ~10 minutes)
- Upload your account list, contacts, pipeline, and activity data
- Review Territory Dashboard to see your metrics
- Click through to individual tools as needed
- Refresh data weekly as you update CRM
- Use reports monthly for territory planning
