# BUILD: Proposal Builder Tool

## Purpose
Guided wizard that walks through the proposal building process (Pains → Solution → ROI → Timeline → MS Alignment) and generates a branded, professional one-pager suitable for executive review and approval.

## What This Tool Does
- **Guided Wizard Interface**: Step-by-step proposal building (no blank page syndrome)
- **Pain → Solution Mapping**: Explicitly link customer pains to your Nerdio solution components
- **ROI Calculator**: Auto-calculate cost savings, productivity gains, and payback period
- **Visual Timeline**: Show implementation phases and key milestones
- **Microsoft Alignment**: Show how Nerdio complements and optimizes their Microsoft tech stack
- **Branded Output**: Generate professional one-page proposal PDF with Nerdio branding
- **Template Library**: Save common solutions/ROI models for reuse
- **Version History**: Track proposal iterations for the same deal

## Data You Need to Provide

### 1. Deal Context
- Deal Name / Account Name
- Contact Name & Title
- Current Environment (what solutions are they using?)
- Key Pains/Problems (identified during discovery)
- Budget/Deal Value
- Implementation Timeline (target)

### 2. Nerdio Solution Components
- List Nerdio services/products you're proposing:
  - Azure Virtual Desktop (AVD)
  - Nerdio Manager for Enterprise (NME)
  - Nerdio Manager for Service Providers (NMSP)
  - Azure optimization services
  - Other (custom services)

### 3. Pricing & Costs
- Nerdio licensing cost (annual)
- Implementation cost (if applicable)
- Support cost (if applicable)
- Customer's current IT spend (for comparison)
- Cost of problems they're experiencing (if known)

### 4. ROI Assumptions (provide your typical values)
- Productivity improvement %
- IT staff time saved per month (hours)
- Help desk ticket reduction %
- Infrastructure cost savings per month
- Security incident prevention value

**Example context:**
```
Deal: Acme Corp DaaS Migration
Contact: Sarah Johnson, VP IT
Current: Citrix + on-prem, 2500 users
Pains: Rising infrastructure costs, user experience issues, security gaps
Budget: 250,000 EUR
Timeline: 6 months
```

## Prompt for Claude

Copy and paste this prompt into Claude, replacing the bracketed sections with your data:

---

**I need you to create a Proposal Builder Tool for creating customer proposals.**

Please build a single-file HTML application with all CSS and JavaScript embedded that includes:

**Core Features:**
1. **Wizard-Style Interface**:
   - Step-by-step guided wizard that walks through proposal creation
   - Steps: Deal Setup → Pains → Solution → ROI → Timeline → Microsoft Alignment → Preview & Export
   - Progress indicator showing current step
   - Next/Previous navigation
   - Auto-save to browser memory at each step

2. **Step 1 - Deal Setup**:
   - Form fields:
     - Deal name / Account name
     - Contact name & title
     - Contact email (optional)
     - Deal value / Budget
     - Implementation target date
     - Current environment description (how many users, current platforms, etc.)
   - Upload logo or company info (optional)

3. **Step 2 - Pains & Problems**:
   - List key pains discovered during discovery:
     - Pain description (e.g., "Rising infrastructure costs", "User experience issues")
     - Business impact (quantified if possible: "costing $50K/year", "causing 2000+ help desk tickets/month")
     - Affected stakeholder (end user, IT, executive, finance)
     - Add/remove pain items dynamically
   - Later steps will map solutions to these pains

4. **Step 3 - Solution Design**:
   - Show available Nerdio solution components:
     - Azure Virtual Desktop (AVD) Migration
     - Nerdio Manager for Enterprise (NME)
     - Cost Optimization Services
     - Security & Compliance
     - Other (custom)
   - For each solution component selected, allow user to:
     - Describe how it addresses the customer's pains
     - Map to 1-3 specific pains from Step 2 (link solution to pain)
     - Add implementation details (e.g., "5-phase migration, starting with pilot group")
   - Show how selected solutions address all identified pains
   - Alert if any pain is not addressed by selected solutions

5. **Step 4 - ROI & Business Case**:
   - Input business metrics:
     - Current IT annual spend: $[amount]
     - Current pain-related costs: $[amount] (e.g., $50K annual infrastructure overspend)
   - ROI assumptions (allow user to customize):
     - Infrastructure cost savings: [%] per month / $[amount]
     - IT staff productivity improvement: [%] (hours saved per month)
     - Help desk efficiency: [%] reduction in tickets / $[amount] savings
     - Security/risk savings: $[amount] avoided incident costs
     - User productivity improvement: [%] / $[amount] business value
   - Auto-calculate:
     - Annual cost of Nerdio solution
     - Annual savings and benefits
     - Net annual benefit
     - Payback period (months)
     - 3-year ROI
   - Display ROI summary with clear numbers
   - Show sensitivity (if productivity improvement was 5% instead of 10%, ROI is still X%)

6. **Step 5 - Implementation Timeline**:
   - Visual timeline builder:
     - Phase 1: Discovery & Planning (1 month typical)
     - Phase 2: Pilot Setup (4-6 weeks typical)
     - Phase 3: Pilot Validation (2-3 weeks typical)
     - Phase 4: Production Migration (4-8 weeks typical)
     - Phase 5: Optimization & Support (ongoing)
   - Allow customization of phase names, durations, and sequencing
   - Show go-live date based on phases selected
   - Key milestones in each phase (e.g., "Pilot group cut over to AVD", "All users migrated", "Production optimization complete")
   - Dependencies and critical path

7. **Step 6 - Microsoft Alignment**:
   - Show how Nerdio solution leverages their existing Microsoft tech stack
   - Interactive checklist:
     - "How will this use Azure more effectively?" (checkboxes: VMs, networking, monitoring, backup, etc.)
     - "How will this enhance Office 365?" (checkboxes: Intune integration, Teams optimization, etc.)
     - "Security benefits with Microsoft stack" (checkboxes: conditional access, MFA, threat detection, etc.)
     - "Microsoft licensing optimization" (describe how Nerdio helps optimize their Microsoft spend)
   - Generate narrative: "Your Nerdio solution integrates with your existing Azure and Office 365 environment, leveraging your Microsoft investments while optimizing costs and security."

8. **Step 7 - Preview & Customize**:
   - Live preview of final proposal one-pager
   - Edit text fields directly in preview
   - Adjust colors (Nerdio brand colors: Navy #0B1B3D, Teal #00B4D8, Green #00C48C)
   - Finalize before exporting

9. **Proposal Output (One-Page Format)**:
   - Professional PDF/HTML output with:
     - **Header**: Company logo, date, "Proposal for [Account Name]"
     - **Executive Summary** (2-3 sentences): What are you proposing and why?
     - **Current Situation** (2-3 bullets): Their current environment and challenges
     - **Proposed Solution** (3-4 bullets): What Nerdio provides and how it solves pains
     - **Business Benefits** (4-5 bullets): Key ROI and business outcomes
     - **Implementation Timeline** (visual or text): Key phases and go-live date
     - **Financial Summary** (table):
       - Annual Nerdio cost
       - Annual savings and benefits
       - Net annual benefit
       - Payback period
       - 3-year total value
     - **Microsoft Alignment** (2-3 sentences): How this leverages their Microsoft stack
     - **Next Steps** (3 bullets): What happens next and contact info
   - Branded with Nerdio colors (Navy, Teal, Green)
   - Clean, professional layout suitable for C-level review
   - Single page (fits on one side of 8.5"x11" or A4 paper)

10. **Export Options**:
    - Download as PDF (print-ready)
    - Download as HTML (email-friendly)
    - Email directly to contact (if email provided)
    - Save proposal for later editing (browser storage)

11. **Template Library**:
    - Save completed proposal as template for reuse
    - Library of pre-built ROI models (e.g., "Typical AVD Migration", "Cost Optimization", "SMB to Enterprise")
    - Quick-start proposals based on solution type selected
    - Edit and customize templates

12. **Version Control**:
    - Track proposal iterations
    - Show "Last updated: [date]"
    - Version history (allows reverting to previous version if needed)

**Visual Design**:
- Use Nerdio brand colors: Navy (#0B1B3D) for headers, Teal (#00B4D8) for highlights, Green (#00C48C) for positive metrics/benefits
- Professional, clean layout throughout wizard
- Progress indicator at top showing which step you're on
- Step-by-step pacing (not overwhelming)
- Large, clear buttons (Next, Back, Export)
- Real-time preview of proposal output
- Print-friendly design for proposal output

**Data Handling**:
- Store wizard data in browser memory at each step
- Auto-save progress (doesn't lose data if browser closes)
- Validate required fields before allowing next step
- Calculate ROI dynamically as user inputs data
- Generate professional PDF output

---

## Tips for Success
1. **Data-Driven**: Reference specific discovery findings (pains, current environment, stakeholder quotes)
2. **ROI Realistic**: Use conservative ROI assumptions; better to under-promise and over-deliver
3. **Pain-Solution Mapping**: Explicitly show which solution addresses which pain (answers "why this?")
4. **Executive Focused**: One-pager is for VP/CFO/Executive sponsor - focus on business value, not technical details
5. **Numbers Matter**: CFO wants to see financial impact; include all benefits (cost savings + business value)
6. **Timeline Credible**: Implementation timeline should be realistic based on project scope

## ROI Assumption Guidelines
- **Infrastructure Savings**: Typical 30-50% reduction in VM/infrastructure costs when moving to optimized Azure + Nerdio
- **IT Staff Productivity**: Typical 10-15 hours/week saved in infrastructure management with Nerdio automation
- **Help Desk Reduction**: Typical 20-30% reduction in support tickets with improved VDI performance/stability
- **User Productivity**: Typical 2-5% productivity improvement from better VDI experience (conservative estimate)
- **Payback Period**: Good proposals show 6-12 month payback even with conservative assumptions

## One-Pager Golden Rules
1. **One page** = They'll actually read it (longer proposals get delegated/ignored)
2. **Numbers first** = CFO wants ROI, payback, annual benefit prominently
3. **Pain-solution matching** = Answers why this, not just what
4. **No tech jargon** = VPs don't care about technical details; they care about business impact
5. **Next steps clear** = What happens if they approve? When does implementation start?

## Common Proposal Mistakes to Avoid
- Too much technical detail (not what CFO wants to read)
- No ROI numbers (make the business case explicit)
- Weak pain-solution mapping (doesn't answer "why this for us?")
- Unrealistic timeline (kills credibility)
- No clear next steps (leaves them wondering what to do)

## Next Steps
- Generate your personalized Proposal Builder using the prompt above
- Build your first proposal using the wizard
- Export proposal as PDF and review with sales manager
- Get feedback on proposal messaging and ROI assumptions
- Build 2-3 proposals with actual deals to refine your messaging
- Use proposal templates for future similar deals
