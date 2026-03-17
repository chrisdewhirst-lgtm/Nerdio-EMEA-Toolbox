# BUILD: ICP Profiler Tool

## Purpose
Creates ideal customer profiles (ICPs) with weighted scoring criteria to rank and identify territory accounts that best match your target persona. This tool helps you focus prospecting efforts on accounts with highest conversion likelihood.

## What This Tool Does
- **ICP Builder**: Define your ideal customer profile with customizable weighted criteria
- **Fit Scoring**: Automatically scores all territory accounts against your ICP definition
- **Account Ranking**: Ranks accounts by fit score to identify best prospects
- **Persona Matching**: Visual comparison of each account against your ideal profile
- **Propensity Modeling**: Highlights which attributes make accounts good/poor fits
- **Territory Insights**: Shows distribution of fit scores across your territory

## Data You Need to Provide

### 1. Territory Account List (CSV format)
Export from your CRM with these columns:
- Account Name
- Employee Count
- Industry Code (or Industry Name)
- Revenue/ARR (if available)
- Current Tech Stack (comma-separated, e.g., "Azure,Office365,Citrix,VMware")
- Department Structure (number of departments/business units)
- Geographic Location (Country/Region)
- Recent Growth Rate (%) (optional)

**Example CSV format:**
```
Account Name,Employee Count,Industry,ARR,Current Tech Stack,Departments,Location,Growth Rate
Global Finance Inc,3500,Banking,500000,Azure Office365,15,UK,8
NextGen Tech Ltd,450,Software,120000,Azure AWS,4,Germany,15
Retail Solutions EU,2200,Retail,180000,VMware Citrix,8,France,3
```

### 2. Your ICP Definition (provide in conversation or via spreadsheet)
Think about:
- **Ideal company size** (employee count range)
- **Target industries** (which sectors buy most from Nerdio?)
- **Average revenue range**
- **Technology stack preferences** (what tools do your best customers use?)
- **Organizational structure** (centralized IT vs. federated?)
- **Growth characteristics** (fast-growing, stable, declining?)

## Prompt for Claude

Copy and paste this prompt into Claude, replacing the bracketed sections with your data:

---

**I need you to create an ICP Profiler Tool for my Nerdio territory.**

Please build a single-file HTML application with all CSS and JavaScript embedded that includes:

**Core Features:**
1. **Data Import**:
   - Upload CSV file with account data including Account Name, Employee Count, Industry, ARR, Current Tech Stack, Departments, Location, and Growth Rate
   - Define or import ICP criteria with weighted importance scores

2. **ICP Definition Interface**:
   - Allow users to input or adjust ICP criteria with sliders for weight allocation
   - Editable criteria like: target employee count range, preferred industries, technology stack preferences, department count range, growth rate preferences
   - Weight distribution should total 100% across all criteria
   - Save/load ICP definitions for reuse

3. **Fit Scoring Engine**:
   - Score each account on how well it matches the defined ICP (0-100 scale)
   - Show scoring breakdown: employee count match (%), industry match (%), tech stack match (%), structure match (%), growth match (%)
   - Apply weighting to calculate final fit score
   - Visual indicator showing how each account scores on each criterion

4. **Account Ranking Dashboard**:
   - Table showing all accounts ranked by fit score (highest first)
   - Columns: Rank, Account Name, Fit Score, Industry, Employee Count, ARR, Key Strengths, Gaps vs ICP
   - Color-coding: Green (>75 fit), Amber (50-74 fit), Red (<50 fit)
   - Sortable by any column

5. **ICP Comparison Cards**:
   - Click any account to see detailed comparison against ICP
   - Show account profile side-by-side with ICP ideal profile
   - Highlight matching attributes in green, gaps in red
   - Show which ICP criteria the account excels at
   - Show improvement areas (what would make this a better fit)

6. **Territory Distribution Analysis**:
   - Pie chart showing % of accounts in each fit band (High/Medium/Low)
   - Industry distribution vs ICP preferences
   - Employee size distribution vs ICP target
   - Tech stack analysis: which technologies are common in your territory vs in your ICP

7. **Actionable Insights**:
   - Top 10 accounts by fit score (high-priority prospects)
   - Accounts with high growth rate + moderate fit (growth opportunities)
   - Accounts close to fit threshold (could be good targets with the right approach)
   - Industry opportunities (industries you target but have low penetration in)

**Visual Design:**
- Use Nerdio brand colors: Navy (#0B1B3D) for headers, Teal (#00B4D8) for highlights, Green (#00C48C) for fit indicators, White (#FFFFFF) for backgrounds
- Clean comparison view with clear visual distinction between ICP ideal and actual accounts
- Use progress bars to show fit score across criteria
- Responsive design for desktop and tablet

**Data Handling:**
- Parse CSV file uploads
- Store ICP definition and scores in browser memory
- Allow export of ranked accounts list as CSV
- Validate numeric inputs (employee count, ARR, growth rate)
- Handle missing values gracefully

---

## Tips for Success
1. **Start Simple**: Begin with 3-5 key ICP criteria, add more as you refine
2. **Industry Codes**: Use consistent industry classification (NAICS, industry names, or your own categories)
3. **Tech Stack**: List technologies without version numbers (e.g., "Azure", not "Azure 2024")
4. **Weight Allocation**: Put higher weight on criteria that best predict customer success (usually size + industry fit)
5. **Test Your ICP**: Compare it against your recent wins — does your highest-fit accounts match your best customers?
6. **Iterate**: Refine ICP weights quarterly based on actual win/loss data

## Common ICP Profiles
- **Enterprise IT Services**: Large employees (1000+), tech-forward industries, distributed departments, high growth
- **Mid-Market Professional Services**: 200-1000 employees, diverse industries, moderate growth, Azure/Office365 users
- **Vertical-Specific**: Tight industry focus, specific tech stack requirements, revenue threshold

## Next Steps
- Generate your personalized ICP Profiler using the prompt above
- Define your ideal customer profile based on your best customers
- Upload your territory account data as CSV
- Identify top-20 high-fit accounts for outreach campaign
- Use ICP Profiler to qualify new accounts as they enter your territory
