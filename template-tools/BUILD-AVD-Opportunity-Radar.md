# BUILD-AVD-Opportunity-Radar

## Purpose
Create a territory-specific AVD opportunity dashboard that combines account intelligence with deal prioritization, account tiers, and engagement status. Sales teams use this to identify high-value accounts, track RDS migration signals, and manage AVD pipeline by account tier.

## What This Tool Does
The AVD Opportunity Radar displays a prioritised list of accounts in your territory with:
- **Account tiers** (T1 Prime, T2 Strong, T3 Possible) based on scoring
- **Opportunity signals** (RDS CAL estate size, DaaS spend, Intune usage, active deals)
- **Engagement metadata** (Microsoft co-sell alignment, customer status, partner engagement)
- **Interactive scoring** showing account fit for AVD migrations
- **Detail panels** with custom messaging, talk tracks, and next actions

This is a customizable template — you supply your account list and Nerdio will generate your personalized dashboard.

## Data You Need to Provide

### 1. Account List (CSV or JSON format)
For each account, provide:
- **Company Name** (e.g., "Lloyds Banking Group")
- **Industry** (e.g., "Financial Services", "Retail & Consumer Goods")
- **Territory/Country** (e.g., "United Kingdom", "Ireland")
- **Employees** (headcount, optional)

### 2. Opportunity Signals
For each account, estimate:
- **RDS CAL Range** (e.g., "10,000–25,000", "2,500–5,000", or "0–100" if minimal)
- **DaaS/VDI Annual Spend** (e.g., "500K–1M", "1M–10M")
- **Intune/M365 MAU Count** (e.g., ">50,000", "10,000–25,000")
- **E5/E3 EA Licences** (Yes/No)
- **Active AVD Deal Amount** (£ or $ value, or blank if none)

### 3. Engagement Status
For each account:
- **Customer Status** (existing Nerdio customer: Yes/No)
- **Microsoft Engagement** (Microsoft co-sell conversation active: Yes/No)
- **Customer Engagement** (active customer conversation: Yes/No)
- **Partner Engagement** (named partner on account: Yes/No)

### Example Data Format
```csv
Name,Industry,Country,Employees,RDS_CAL,DaaS_Spend,Intune_MAU,E5_License,Active_Deal,MS_Engaged,Customer
Lloyds Banking,Financial Services,UK,62000,25000-50000,1M-10M,>50000,Yes,5M-10M,No,Yes
Unilever,Retail & Consumer Goods,UK,116000,25000-50000,1M-10M,>50000,Yes,1M-5M,No,No
Sainsbury's,Retail & Consumer Goods,UK,60000,2500-5000,1M-10M,10000-25000,Yes,500K-1M,No,No
```

## Prompt for Claude

Copy and paste this to Claude, updating the `[DATA]` section with your account list:

---

**Create an AVD Opportunity Radar dashboard for my territory with this account data:**

```
[PASTE YOUR ACCOUNT DATA HERE — CSV or JSON format]
```

**Requirements:**
1. Single-file HTML app with all CSS and JavaScript inline
2. Navy header (#0B1B3D) with teal border (#00B4D8), using Nerdio branding
3. Three-tier filtering: T1 Prime (score 30+), T2 Strong (20–29), T3 Possible (<20)
4. Additional filters: Active Deal, Microsoft Engaged, Industry filters
5. Account cards showing:
   - Company name + country
   - Tier badge (T1/T2/T3) with color-coded top border
   - Circular fit score (0–100)
   - Signal tags: RDS CAL range, DaaS spend, active deal, Intune usage, E5/E3 status
   - Small engagement chips (Customer, Microsoft, Partner icons)
6. Click any card to open side panel with:
   - Full account details (employees, RDS CALs, DaaS spend, Intune MAU)
   - AVD fit score explanation
   - Custom messaging based on signals (RDS migration hook, FSI compliance angle, co-sell narrative, etc.)
   - Suggested next actions (Request co-sell intro, Research renewal dates, Brief SDR, Check partner coverage)
   - Talk tracks / objection handling
7. Top stats: Total T1/T2/T3 count + active deals in territory
8. Search bar for account name/industry filtering
9. Responsive design, works on desktop and tablet
10. Nerdio branding: navy + teal + green accents (#00C48C), white text

**Output:** Save as single HTML file, ready to share with sales team for territory planning and account prioritization.

---

## Tips for Success

- **Scoring logic:** Combine RDS CAL size (40%), DaaS annual spend (25%), engagement signals (20%), and company size (15%). Accounts with active deals or Microsoft co-sell alignment bump up by +10 points.
- **Talk tracks matter:** The detail panel is where value lives — customize the messaging for FSI (compliance angle), Retail (seasonal scaling), or other verticals based on your territory.
- **Keep it live:** Update the data quarterly as deals close or new signals emerge. The tool makes it easy to track progress.
- **Share with leadership:** Territory forecasting becomes visual — show your pipeline by tier and deal status.

---

## Nerdio Branding

- Primary Navy: `#0B1B3D`
- Accent Teal: `#00B4D8`
- Highlight Green: `#00C48C`
- Text: White `#FFFFFF`

Use these colors for buttons, badges, borders, and highlights to maintain consistency with Nerdio visual identity.

---

## Output
A single-file HTML dashboard ready to load in any web browser. Share the file via Teams, email, or upload to your internal tools platform. No backend required — all filtering and sorting happens client-side.
