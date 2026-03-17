# BUILD-FSI-Battlecard

## Purpose
Create a sales battlecard for the Financial Services Industry (FSI) vertical. This is a 1-page (A4 landscape) template that sales teams print and reference during customer calls. It includes key differentiators, ROI talking points, competitive comparisons, and objection handlers specific to banking, insurance, and wealth management organizations.

## What This Tool Does
The FSI Battlecard provides:
- **FSI Pain Points** — Legacy Citrix costs, Windows 11 migration risk, PRA/FCA compliance burden, Azure sprawl, zero-tolerance for downtime, security breach risk
- **Four Pillars of Nerdio Solution** — Automate (1-hour deployment), Optimize Cost (55% savings), Secure & Comply (CIS baselines, audit-ready), Visibility (unified dashboard)
- **FSI Use Cases** — Citrix/VMware exit, Windows 11 rollout, patch compliance, Azure cost control
- **Proof Points** — Customer case studies (Willis Towers Watson, LexisNexis, Grant Thornton, etc.) with specific ROI metrics
- **Objection Handlers** — Responses to "We'll use native Azure", "We're mid-Citrix contract", "Data residency concerns", "Is this Microsoft-backed?"
- **Key Numbers** — 55% avg cost savings, <1hr deployment, 75% fewer support tickets, 62 published case studies, customer count, valuation
- **Microsoft Relationship** — Scott Manchester (CPTO, 25 yrs AVD leadership), Microsoft Partner of the Year 2025, co-sell aligned
- **Discovery Questions** — What to ask during discovery calls (VDI cost, compliance proof, failure response, provisioning time)
- **Next Steps** — Free cost estimator, 30-day trial, FSI reference calls, Azure Marketplace deploy option

## Data You Need to Provide

### 1. FSI Customer Proof Points
For each case study:
- **Customer Name** (e.g., "Willis Towers Watson", "LexisNexis")
- **Industry Sub** (e.g., "Global FSI Firm", "Legal Information Services")
- **Key Result #1** (e.g., "50% YoY cost savings")
- **Key Result #2** (e.g., "Support tickets down 75%")
- **Key Result #3** (optional, e.g., "User satisfaction: 35 → 90+/100")

### 2. Nerdio Messaging for FSI
- **Core value proposition** (e.g., "Deploy compliant cloud desktop environments in hours, not months")
- **Key differentiators vs Citrix** (native Azure, patented auto-scaling, governance built-in)
- **Key differentiators vs native Azure** (finished product vs building blocks, CIS baselines, compliance evidence ready)
- **Compliance talking points** (PRA operational resilience, FCA evidence, continuous patch proof, audit trails)

### 3. Product & Pricing Information
- **Product name & version** (e.g., "NME v7.6")
- **Capabilities** (manages AVD, Windows 365, Intune)
- **Azure support** (Azure Government, Azure Local supported)
- **Website/CTA** (e.g., "getnerdio.com")

### Example Data Format
```csv
Customer,Vertical,Result_1,Result_2,Result_3
Willis Towers Watson,Global FSI Firm,Deployed at scale across multiple regions,Multiple geographies,—
LexisNexis,Legal Information Services,50% YoY cost savings,Support tickets down 75%,User satisfaction 35→90+
Grant Thornton,Big 4 Advisory,£20K/month saved,AVD live in days,Expanding across 3 countries
Kraft Heinz,Diversified Manufacturing,Active Nerdio customer,—,—
Chevron,Energy,Active Nerdio customer,—,—
```

## Prompt for Claude

Copy and paste this to Claude, updating the `[DATA]` section:

---

**Create an FSI Battlecard (A4 landscape) with this data:**

```
[PASTE YOUR FSI PROOF POINTS HERE]

Product: NME v7.6
Website: getnerdio.com
Capabilities: Manages AVD, Windows 365, Intune from one interface
```

**Requirements:**
1. Single-file HTML app designed to print as A4 landscape (297mm × 210mm)
2. All CSS and JavaScript inline
3. Navy header (#0B1B3D) with teal accents (#00B4D8), Nerdio branding
4. Three-column layout:
   - **LEFT COLUMN** (Navy background #0B1B3D):
     - Section: "The FSI Challenge" — 7 key pain points (legacy Citrix, Windows 11 risk, PRA/FCA, Azure sprawl, downtime intolerance, security breaches, manual audit reporting)
     - Pain point list with ✕ icon
     - Section: "FSI Proof Points" — Customer name + key results (Willis Towers Watson, LexisNexis, Grant Thornton, etc.)
   - **CENTRE COLUMN** (White background, bordered):
     - Teaser: "The Nerdio Answer — Four Pillars"
     - Four pillar grid (2×2): ⚡ Automate | 💰 Optimise Cost | 🔒 Secure & Comply | 👁 Visibility
     - Each pillar: icon + title + 1-2 line description
     - Section: "FSI Use Cases" — Tagged use cases (Citrix/VMware Exit, Windows 11 Rollout, Patch Compliance, Azure Cost Control) with brief description
   - **RIGHT COLUMN** (Navy background #0B1B3D):
     - Section: "Objection Handling" — 4–5 Q&A pairs (expandable or always-visible)
     - Section: "Key Numbers" — 4 mini-stats (55% savings, <1hr deploy, 75% fewer tickets, 62 case studies)
     - Section: "Microsoft Relationship" — Scott Manchester, Gavriella Schuster, Partner of the Year, co-sell aligned, Azure Marketplace
5. Footer stripe (3-column):
   - **Column 1:** "Discovery Questions" — 4 key questions to ask (VDI cost, compliance proof, failure response, provisioning time)
   - **Column 2:** "Next Steps" — 4 action items (Free cost estimator, 30-day trial, FSI reference call, Azure Marketplace)
   - **Column 3:** "Product & Contact" — NME version, capabilities, Azure support, website CTA
6. Print-friendly styling: works perfectly on A4 landscape, no page breaks mid-content
7. Branding: Navy + Teal + Green with white text, compact but readable typography
8. Optional: QR code or URL in footer for digital reference

**Output:** Single HTML file optimised for printing. Save as PDF from browser for distribution to sales team.

---

## Tips for Success

- **Proof points matter:** Real numbers (% savings, support ticket reduction, ROI payback) beat generic claims. If you have a Willis Towers Watson reference, feature it prominently.
- **Make it printable:** Your reps carry this into customer meetings. Test printing on an A4 printer to ensure it looks professional.
- **Objection handlers should be short:** Your rep reads this in 10 seconds before answering a customer objection.
- **Front-load FSI pain:** The left column is the hook — "We understand your PRA compliance burden, audit trail nightmare, and legacy Citrix costs."
- **Update quarterly:** As new customers come on board or new success metrics emerge, refresh the proof points.

---

## Nerdio Branding

- Primary Navy: `#0B1B3D`
- Accent Teal: `#00B4D8`
- Highlight Green: `#00C48C`
- White: `#FFFFFF`

---

## Output
A single-file HTML document. Print to PDF and distribute to your FSI sales team. This is their 1-page reference guide for every FSI customer conversation.

---

## This is a Template

Once you've created your FSI battlecard, use this same template to create battecards for other verticals:
- **Insurance Battlecard** — Insurance-specific pain points, proof points, use cases, objections
- **Retail Battlecard** — Seasonal scaling, POS integration, multi-location management
- **Healthcare Battlecard** — Patient data, HIPAA compliance, shift work patterns
- **Higher Ed Battlecard** — Student device lifecycles, remote learning, compliance
- **Manufacturing Battlecard** — Supply chain continuity, shift work, rugged environments

Each battlecard is a single HTML file — customise the pain points, use cases, and proof points for your vertical.
