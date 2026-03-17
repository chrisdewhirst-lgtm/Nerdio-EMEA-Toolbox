# BUILD-Microsoft-Account-Intelligence

## Purpose
Create a Microsoft account intelligence tool that maps the Microsoft hierarchy at target accounts, shows internal team structure, and provides co-sell engagement strategies. This bridges the gap between your sales team and the Microsoft account team, enabling coordinated go-to-market motions.

## What This Tool Does
The Microsoft Account Intelligence dashboard provides:
- **Account hierarchy** — Microsoft account executive, account team, and regional team structure
- **Role mapping** — Decision makers, technical architects, procurement, and their Microsoft points of contact
- **Co-sell alignment strategies** — How to position Nerdio in the Microsoft deal, unlock co-sell funding, and register as a partner opportunity
- **Talk tracks** — Microsoft co-sell positioning, Windows 365 vs AVD narrative, and regulated industry angles (FSI, healthcare)
- **Team tracking** — Who at Microsoft owns this account, how to escalate, joint planning calendar
- **Territory-specific examples** — Real account examples showing successful co-sell playbooks

This is a lookup and planning tool for your sales team to prepare for Microsoft conversations and coordinate co-sell registrations.

## Data You Need to Provide

### 1. Microsoft Accounts (Target Accounts at Your Territory)
For each account you want to co-sell with Microsoft:
- **Account Name** (e.g., "Barclays")
- **Microsoft Account Executive Name** (if known, or role title)
- **Microsoft Account Team** (Team names: GBBS, FSI, Commercial, Public Sector, etc.)
- **Microsoft Region** (e.g., "UK/Ireland", "EMEA", "Global")
- **Account Size/Revenue** (enterprise, mid-market, SMB)

### 2. Nerdio Engagement Strategy
For each account:
- **Co-sell Narrative** (How does Nerdio fit with Microsoft AVD/W365 strategy?)
- **Differentiation vs Competitors** (vs Citrix, vs native Azure, vs other ISVs)
- **Customer Pain Point** (RDS migration, Windows 11 compliance, cost control, multi-tenant management)
- **Microsoft Funding Opportunity** (MCI, co-sell eligible, MACC alignment)
- **Regulatory Angle** (If FSI: DORA/PRA/FCA; if Healthcare: HIPAA; if Retail: none typically)

### 3. Engagement Talking Points
For each account vertical (FSI, Retail, Healthcare, etc.):
- **Opening message** (e.g., "Nerdio is the co-sell motion that completes the Microsoft AVD story")
- **Objection handlers** (e.g., "We'll use native Azure" → "Native Azure gives building blocks, Nerdio gives the finished product")
- **Reference customers** (e.g., "We have FSI customers like Willis Towers Watson")

### Example Data Format
```csv
Account,Microsoft_AE,Microsoft_Team,Region,Vertical,Account_Size,Pain_Point,Cosell_Angle
Barclays,James Moon,GBBS,UK/Ireland,FSI,Enterprise,Citrix EOL + 100K W365 deployment,AVD/W365 governance layer
Schroders,Nicki Farrell,FSI,EMEA,FSI,Enterprise,Active PoV + compliance requirements,Unlock MCI funding on NME Premium
Kingfisher,Unknown,Commercial,UK,Retail,Enterprise,Multi-brand desktop rationalisation,Joint Computacenter + Microsoft + Nerdio play
```

## Prompt for Claude

Copy and paste this to Claude, updating the `[DATA]` section:

---

**Create a Microsoft Account Intelligence lookup tool for my territory with this data:**

```
[PASTE YOUR ACCOUNT DATA HERE — CSV or JSON format]
```

**Requirements:**
1. Single-file HTML app with all CSS and JavaScript inline
2. Navy header (#0B1B3D) with teal accents (#00B4D8), Nerdio branding
3. Search box to find accounts by name — shows dropdown with account list
4. For each account, display:
   - Account name and size (Enterprise/Mid-Market/SMB)
   - Microsoft Account Executive name and team
   - Microsoft region and strategic classification
5. Expandable sections for each account showing:
   - **Team Structure** — Microsoft AE + account team (grid layout, role + avatar)
   - **Nerdio Co-Sell Positioning** — How Nerdio fits, why this account is a co-sell priority
   - **Talk Tracks** — Ready-to-use talking points for co-sell pitch, reference customers, objection handlers
   - **Next Steps** — Co-sell registration guidance, funding opportunities, joint planning calendar recommendation
6. Copy-to-clipboard buttons for talk tracks and positioning statements
7. Chips for filtering: By vertical (FSI, Retail, Healthcare), by Microsoft team (GBBS, Commercial), by region
8. Show co-sell eligible badge (green #00C48C) for accounts with high potential
9. Responsive design, works on desktop
10. Branding: Navy + Teal + Green with white text

**Output:** Single HTML file, ready to share with your sales team for pre-call prep and Microsoft engagement planning.

---

## Tips for Success

- **Talk tracks are critical:** Prepare 3–5 key talking points for each vertical (FSI compliance angle, Retail seasonal scaling, etc.).
- **Make it searchable:** Your team should find an account in 5 seconds, then have a 2-minute read on the co-sell strategy.
- **Keep Microsoft team names accurate:** Different regions have different Microsoft team structures (GBBS = Global Banking & Financial Services, FSI = Financial Services Industry vertical, Commercial = mid-market).
- **Update before territory planning:** Run this before quarterly business reviews so your team knows which accounts to co-sell register.

---

## Nerdio Branding

- Primary Navy: `#0B1B3D`
- Accent Teal: `#00B4D8`
- Highlight Green: `#00C48C`
- White: `#FFFFFF`

---

## Output
A single-file HTML reference guide. Store in Teams, Confluence, or shared drives. This is a lookup tool — your team uses it to prepare for Microsoft calls and ensure consistent co-sell messaging across the territory.
