# BUILD-CoSell-Territory-Intelligence

## Purpose
Create a comprehensive co-sell account prioritization tool that combines account cards, team tracking, opportunity scoring, and engagement strategies. This is the master dashboard for territory co-sell planning — showing which accounts to register with Microsoft, why they matter, and the exact co-sell play for each.

## What This Tool Does
The CoSell Territory Intelligence dashboard provides:
- **Account cards with priority bands** — P1 (Act Now), P2 (Build Pipeline), P3 (Nurture)
- **Scoring methodology** — RDS CAL + DaaS spend + intent signals (6sense data) + engagement status
- **Co-sell registration guidance** — Which accounts to register in Partner Center, urgency level, and expected Microsoft funding
- **Engagement strategies** — Specific co-sell narratives per account (Citrix exit, W365 risk mitigation, governance angle, etc.)
- **Team accountability tracking** — Microsoft AE name, Nerdio account lead, suggested next action, timeline
- **Microsoft play narrative** — How to position Nerdio as the control layer that makes AVD/W365 enterprise-ready
- **Vertical-specific angles** — FSI compliance, Retail seasonal burst, Healthcare patient data, Insurance consolidation post-M&A

This is your go-live dashboard for co-sell territory execution.

## Data You Need to Provide

### 1. Target Accounts for Co-Sell
For each account you want to co-sell with Microsoft:
- **Account Name** (e.g., "Barclays")
- **Vertical** (FSI, Insurance, Retail, Healthcare, etc.)
- **Sub-category** (e.g., "Retail Bank", "Retail & Consumer Goods", "Asset Management")
- **Headcount/Size descriptor** (e.g., "83,500 UK staff", "~6,000 staff")
- **Existing customer?** (Yes/No — if Nerdio customer)

### 2. Opportunity Scoring Data
For each account:
- **RDS CAL Estate** (e.g., "25K–50K", "10K–25K")
- **DaaS/VDI Annual Spend** (e.g., "100K–500K", "1M–10M")
- **6sense Intent Score** (0–100, if available; e.g., 96 = actively researching)
- **Priority Tier** (P1 = Active deal / high intent, P2 = Build pipeline, P3 = Nurture)

### 3. Co-Sell Angle & Messaging
For each account:
- **Co-Sell Why** (Specific reason to register: active deal, inherited pipeline, high 6sense intent, M&A risk, Windows 365 exposure, compliance urgency)
- **Microsoft Play** (Who to approach at Microsoft, what Microsoft team owns the account, what funding/support to request)
- **Key Signals** (Tags like "Active Deal", "High RDS", "High Intent", "W365 Risk", "Customer", "FSI", "Insurance", "Retail")

### Example Data Format
```csv
Name,Vertical,Sub,Headcount,Existing_Customer,RDS_CAL,DaaS_Spend,Intent_Score,Priority,CoSell_Why,MS_Play,Tags
Barclays,FSI,Retail Bank,83500 UK,No,25K-50K,100K-500K,89,P1,Active deal £5-10M + 100K M365 Copilot,Register Partner Center + warm intro to GBBS AE,active-deal|rds|intent
Schroders,FSI,Asset Management,~6000,No,2.5K-5K,50K-100K,97,P1,Active PoV in flight,Engage Microsoft PDM for co-present,intent|active-deal|rds
Kingfisher,Retail,B&Q/Screwfix,80000+,No,5K-10K,50K-100K,72,P1,Inherited pipeline + Computacenter SI,Three-way motion with Computacenter,active-deal|rds
Willis Towers Watson,Insurance,Insurance Broker,Unknown,Yes,5K-10K,50K-100K,96,P1,Existing customer + highest intent,Urgent co-sell conversation,customer|intent
```

## Prompt for Claude

Copy and paste this to Claude, updating the `[DATA]` section:

---

**Create a CoSell Territory Intelligence dashboard with this account data:**

```
[PASTE YOUR ACCOUNT DATA HERE — CSV or JSON format]
```

**Requirements:**
1. Single-file HTML app with all CSS and JavaScript inline
2. Navy header (#0B1B3D) with teal border (#00B4D8) and Nerdio branding
3. Filter tabs: By Vertical (FSI, Insurance, Retail, Healthcare, etc.), by Priority (P1, P2, P3)
4. Account cards organised by priority band:
   - **P1 (Act Now)** — Red accent, "Actively research co-sell immediately"
   - **P2 (Build Pipeline)** — Orange accent, "Begin Microsoft account mapping"
   - **P3 (Nurture)** — Amber/Yellow accent, "Register co-sell intent, maintain relationship"
5. Card layout for each account:
   - Company name + sub-category (e.g., "Barclays · Retail & Investment Bank · 83,500 UK staff")
   - Priority score (80–100 range) in circular badge with color gradient
   - Vertical badge (FSI, Insurance, Retail icon/label)
   - Tags showing signals (🔥 Active Deal, 🖥 High RDS, 👁 High Intent, ⚠️ W365 Risk, ✅ Customer, etc.)
   - Opportunity signals grid: RDS CAL count | DaaS spend | 6sense intent score (with color coding)
6. Expandable "Co-Sell Why" narrative:
   - Plain-language explanation why this account matters (active deal, inherited pipeline, high intent, etc.)
   - Specific details (deal size, RDS headcount, compliance trigger, acquisition context)
7. Microsoft Play section:
   - Who to approach at Microsoft (team name, region, suggested AE if known)
   - What funding/support to request (Partner Center co-sell registration, MCI funding, joint exec briefing)
   - Suggested call-to-action (e.g., "Register in Partner Center as co-sell eligible immediately")
8. Header stats: Total accounts | Top accounts by priority | Pipeline value
9. Responsive design, works on desktop and tablet
10. Branding: Navy + Teal + Green with white text; red/orange/amber for priority colors

**Output:** Single HTML file, ready to load in browser. Ready for printing or sharing in Teams/Slack.

---

## Tips for Success

- **Priority assignment is critical:** P1 accounts should have board-level urgency (active deal, inherited pipeline, co-sell funding available). P2 = near-term opportunity (strong signals, Microsoft account exists). P3 = long-term nurture.
- **Co-Sell Why section:** Make it specific. Instead of "Good fit for AVD", say "Active £5–10M deal + 100K M365 Copilot deployment = flagship logo opportunity".
- **6sense Intent Score:** If you have access, include it. Scores >85 = hot prospect, ready for immediate co-sell conversation.
- **Microsoft Play:** Be specific about which Microsoft team owns the account (GBBS for banking, Commercial for mid-market, Public Sector for government, etc.).
- **Update quarterly:** As deals move through pipeline, move accounts between priority tiers and update co-sell strategies.

---

## Nerdio Branding

- Primary Navy: `#0B1B3D`
- Accent Teal: `#00B4D8`
- Highlight Green: `#00C48C`
- Priority Colours:
  - P1 Red: `#DC3545`
  - P2 Orange: `#E07D10`
  - P3 Amber: `#F59E0B`
- White: `#FFFFFF`

---

## Output
A single-file HTML dashboard for territory co-sell planning and execution. Print for account review meetings, share in Teams for team alignment, or embed in your sales portal. This is your master dashboard for which accounts to co-sell register and why.
