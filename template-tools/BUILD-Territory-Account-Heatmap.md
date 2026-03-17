# BUILD-Territory-Account-Heatmap

## Purpose
Create a visual territory heatmap showing account prioritization and engagement status across your geography. This is a macro-level view of your account landscape — showing which accounts are hot (ready to engage), warm (building momentum), or cold (nurture phase).

## What This Tool Does
The Territory Account Heatmap provides:
- **Geographic/categorical heatmap** — Visual display of account engagement status by territory, industry, or custom dimension
- **Heat levels** — Critical (red), High (orange), Medium-High (yellow), Medium (green), Lower (gray) engagement priority
- **Account cards** — Click to see engagement details, opportunity size, recent activity, next steps
- **Filtering & sorting** — By vertical, by engagement level, by RDS estate size, by deal stage
- **Territory intelligence** — Aggregated metrics: total accounts, accounts by priority level, estimated pipeline value
- **Search & navigation** — Find accounts by name, industry, or engagement status

This is your visual dashboard for understanding your account landscape and identifying gaps in coverage.

## Data You Need to Provide

### 1. Account List with Engagement Metadata
For each account in your territory:
- **Account Name** (e.g., "Lloyds Banking Group")
- **Territory** (e.g., "UK", "Ireland", "EMEA" — whatever your geography is)
- **Industry/Vertical** (e.g., "Financial Services", "Retail")
- **Account Size** (Enterprise, mid-market, SMB, or headcount)
- **Engagement Status** (Not engaged, Early stage, Active, Customer, etc.)

### 2. Opportunity & Activity Signals
For each account:
- **Heat Level** (1–5, where 5 = Critical/Red, 1 = Lower/Gray; or: "Critical", "High", "Medium-High", "Medium", "Lower")
- **RDS CAL Estate** (rough size: Small <5K, Medium 5K–25K, Large 25K–50K, Enterprise >50K)
- **DaaS/VDI Spend** (rough size: Minimal, Small, Medium, Large, Enterprise)
- **Deal Stage** (Pipeline, Early, Active, Won, Lost, Nurture)
- **Last Engagement Date** (optional, for sorting by recency)

### 3. Account Context
For each account:
- **Account Owner/Salesperson** (optional, for accountability)
- **Next Action** (e.g., "Schedule discovery", "Send proposal", "Present to SMB", "Close Q2")
- **Notes/Reason for Heat Level** (e.g., "Active AVD PoV", "Inherited deal", "High 6sense intent", "RDS EOL pressure")

### Example Data Format
```csv
Name,Territory,Vertical,Size,Engagement,Heat_Level,RDS_Estate,DaaS_Spend,Deal_Stage,Owner,Notes
Lloyds Banking Group,UK,Financial Services,Enterprise,Customer,5,25K-50K,1M-10M,Active,Chris D,Existing customer + active AVD deal
AIB,Ireland,Financial Services,Enterprise,Not Engaged,5,10K-25K,10K-50K,Active,Chris D,Active deal £10-25M + MS engaged
Barclays,UK,Financial Services,Enterprise,Not Engaged,5,25K-50K,500K-1M,Early,Chris D,Citrix EOL April 2026 + 100K Copilot
Unilever,UK,Retail,Enterprise,Not Engaged,4,25K-50K,1M-10M,Early,Chris D,Seasonal scaling angle
Sainsbury's,UK,Retail,Enterprise,Not Engaged,4,2.5K-5K,1M-10M,Early,Chris D,RDS migration signal
Marks and Spencer,UK,Retail,Enterprise,Not Engaged,4,5K-10K,50K-100K,Nurture,Chris D,Post-cyber incident security focus
John Lewis,UK,Retail,Enterprise,Not Engaged,1,2.5K-5K,Minimal,Nurture,Chris D,Legacy infrastructure, low urgency
```

## Prompt for Claude

Copy and paste this to Claude, updating the `[DATA]` section:

---

**Create a Territory Account Heatmap dashboard with this account data:**

```
[PASTE YOUR ACCOUNT DATA HERE — CSV or JSON format]
```

**Requirements:**
1. Single-file HTML app with all CSS and JavaScript inline
2. Navy header (#0B1B3D) with teal accents (#00B4D8), Nerdio branding
3. Heat level color scale:
   - Level 5 (Critical): Red (#FF3A3A)
   - Level 4 (High): Orange (#FF8C00)
   - Level 3 (Medium-High): Yellow (#F5C800)
   - Level 2 (Medium): Green (#5BB450)
   - Level 1 (Lower): Gray (#9EB8C2)
4. Main heatmap view — cards sized/coloured by heat level:
   - Each card shows account name, territory, vertical, and heat level
   - Card color matches heat level
   - Click to expand for full details
5. Cards for each account display:
   - Account name + territory + vertical + account size
   - Heat level indicator (1–5, color-coded)
   - RDS estate estimate | DaaS spend | Deal stage
   - Account owner / salesperson responsible
   - Last engagement date (if available) or "Not yet engaged"
   - Brief notes on why heat level is assigned (e.g., "Active PoV", "RDS EOL pressure", "Inherited deal")
   - Suggested next action
6. Filter panel:
   - By territory (UK, Ireland, EMEA, etc.)
   - By vertical (FSI, Retail, Healthcare, etc.)
   - By heat level (show only Critical/High/Medium, etc.)
   - By deal stage (Pipeline, Active, Won, Nurture)
7. Search box to find accounts by name
8. Sorting options: By heat level (descending), by territory, by RDS estate, by deal stage
9. Header stats: Total accounts, heat level distribution (5 accounts Critical, 8 High, etc.), total pipeline value
10. Responsive design, works on desktop and tablet
11. Branding: Navy + Teal + Green with heatmap color gradation

**Output:** Single HTML file, ready to load in browser. Perfect for territory planning and account review meetings.

---

## Tips for Success

- **Heat level assignment:** Use a clear framework. Level 5 = accounts with active deals, inherited pipeline, high intent. Level 1 = nurture accounts with low near-term opportunity.
- **Visual impact:** The heatmap should tell a story at a glance — a sea of reds/oranges = hot territory, lots of grays = cold territory needing attention.
- **Update frequency:** Update monthly as deals move through pipeline and new intent signals arrive.
- **Share with leadership:** Use this for territory reviews, forecast calls, and account planning meetings.
- **Track ownership:** If you assign accounts to reps, show owner accountability on each card.

---

## Nerdio Branding

- Primary Navy: `#0B1B3D`
- Accent Teal: `#00B4D8`
- Highlight Green: `#00C48C`
- Heatmap Scale:
  - Level 5 (Critical): `#FF3A3A`
  - Level 4 (High): `#FF8C00`
  - Level 3 (Medium-High): `#F5C800`
  - Level 2 (Medium): `#5BB450`
  - Level 1 (Lower): `#9EB8C2`
- White: `#FFFFFF`

---

## Output
A single-file HTML heatmap dashboard. Load in any browser, share in Teams, or print for account planning sessions. This is your visual territory intelligence tool.
