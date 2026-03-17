# BUILD-CoSell-Target-List

## Purpose
Create a curated co-sell target account list with priority banding, scoring, and engagement strategies. This is a simplified version of the full Territory Intelligence tool — focused on a clean, printable list of targets with co-sell positioning and next steps.

## What This Tool Does
The CoSell Target List provides:
- **Priority bands** — Clear categorization of P1 (Act Now), P2 (Build Pipeline), P3 (Nurture)
- **Account-level scoring** — Fit score based on RDS estate, DaaS spend, intent signals, engagement status
- **Engagement scoring** — Visual indicators of customer status, Microsoft engagement, partner alignment
- **Co-sell narratives** — Plain-language explanation of why each account is a co-sell opportunity
- **Vertical filtering** — Quick view by FSI, Insurance, Retail, Healthcare, etc.
- **Next action steps** — Suggested immediate steps (Register co-sell, Request MS intro, Schedule QBR, etc.)

This is a lightweight, shareable tool for sales teams to quickly identify which accounts to target and how to engage.

## Data You Need to Provide

### 1. Target Accounts
For each account:
- **Account Name** (e.g., "Barclays")
- **Vertical** (FSI, Insurance, Retail, etc.)
- **Size/Headcount** (Enterprise, mid-market, or specific number)
- **Existing Nerdio Customer?** (Yes/No)
- **Priority** (P1, P2, or P3)

### 2. Scoring Components
For each account:
- **RDS CAL Estate** (e.g., "25K–50K" or "High", "Medium", "Low")
- **DaaS/VDI Annual Spend** (e.g., "1M–10M" or "High", "Medium", "Low")
- **Intent Signal** (e.g., "High" = 6sense >80, "Medium" = 60–80, "Low" = <60)
- **Overall Score** (0–100, or let Claude calculate based on components)

### 3. Co-Sell Opportunity Reasons
For each account:
- **Co-Sell Reason** (e.g., "Active deal £5M", "Inherited pipeline", "High 6sense intent", "Post-acquisition consolidation", etc.)
- **Engagement Status** (e.g., "Not yet engaged", "Microsoft engaged", "Partner engaged", etc.)

### Example Data Format
```csv
Name,Vertical,Size,Customer,Priority,RDS,DaaS,Intent,Score,Reason,Engagement
Barclays,FSI,Enterprise,No,P1,25K-50K,1M-10M,High,96,Active deal £5-10M,Not yet engaged
Schroders,FSI,Enterprise,No,P1,2.5K-5K,50K-100K,High,97,Active PoV + intent 97,Microsoft engaged
Willis Towers Watson,Insurance,Enterprise,Yes,P1,5K-10K,50K-100K,High,96,Existing customer + highest intent,Customer engaged
Kingfisher,Retail,Enterprise,No,P1,5K-10K,50K-100K,Medium,88,Inherited pipeline + Computacenter,Not yet engaged
Marks & Spencer,Retail,Enterprise,No,P2,5K-10K,50K-100K,Medium,83,Named MAL + post-cyber,Not yet engaged
Admiral Group,Insurance,Mid-Market,No,P2,2.5K-5K,10K-50K,Medium,82,Named account + strong RDS,Not yet engaged
```

## Prompt for Claude

Copy and paste this to Claude, updating the `[DATA]` section:

---

**Create a CoSell Target List with this account data:**

```
[PASTE YOUR ACCOUNT DATA HERE — CSV or JSON format]
```

**Requirements:**
1. Single-file HTML app with all CSS and JavaScript inline
2. Navy header (#0B1B3D) with teal accents (#00B4D8), Nerdio branding
3. Filter buttons: By vertical (FSI, Insurance, Retail, etc.), by priority (P1, P2, P3), show all
4. Display accounts in priority bands:
   - **P1 — Act Now** (Red badge, count of accounts)
   - **P2 — Build Pipeline** (Orange badge)
   - **P3 — Nurture** (Amber badge)
5. For each account show:
   - Account name + vertical label
   - Size/headcount (e.g., "Enterprise · 83,500 staff" or "Mid-Market")
   - Priority band badge (P1/P2/P3) with color
   - Overall fit score (0–100) in circular indicator
   - RDS CAL estimate | DaaS spend | Intent level (3-column signal grid)
   - Engagement status: ✅ Existing Customer, 🔵 Microsoft Engaged, 👤 Partner Engaged (show applicable)
   - Brief co-sell reason (1–2 sentences: e.g., "Active deal £5M + need for governance", "Inherited pipeline, 6sense intent 97")
6. Quick stats at top: Total P1/P2/P3 count, total target accounts, total pipeline value (if available)
7. Sortable columns: By priority, by score, by RDS estate, by vertical
8. Responsive design, works on desktop and mobile
9. Print-friendly styling (works well on A4/Letter)
10. Branding: Navy + Teal + Green with white text

**Output:** Single HTML file, ready to print or share. Works in any browser.

---

## Tips for Success

- **Keep it concise:** This is a targeting list, not detailed account intelligence. One card = one glance to understand priority and next step.
- **Use visual hierarchy:** Priority badges should jump out — a VP can scan the list in 30 seconds.
- **Make it printable:** Sales teams print this for pipeline reviews, account planning meetings. Ensure it looks good on paper.
- **Update monthly:** As deals close or new intent signals arrive, update scores and priorities.
- **Share widely:** This is your quick-reference guide for reps, managers, and account planners.

---

## Nerdio Branding

- Primary Navy: `#0B1B3D`
- Accent Teal: `#00B4D8`
- Highlight Green: `#00C48C`
- Priority Colours:
  - P1: `#DC3545` (Red)
  - P2: `#E07D10` (Orange)
  - P3: `#F59E0B` (Amber)
- White: `#FFFFFF`

---

## Output
A single-file HTML list. Print it, share it in Teams, embed it in Confluence, or upload to your internal portal. This is your definitive co-sell target list.
