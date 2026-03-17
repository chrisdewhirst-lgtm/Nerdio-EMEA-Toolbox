# BUILD: Meeting Prep Tool

## Purpose
One-click account briefing generator that pulls everything you need before a meeting: account snapshot, buying signals, Microsoft contacts, talking points, and discovery questions tailored to the account's industry and situation.

## What This Tool Does
- **Pre-Meeting Brief**: Generate a one-page executive brief 30 seconds before your meeting
- **Account Snapshot**: Key metrics, current tech stack, org structure at a glance
- **Signal Summary**: Recent buying signals and engagement timeline
- **Microsoft Contact Mapping**: Show Microsoft stakeholders and their roles for joint selling
- **Talking Points**: Dynamic points based on account fit, industry trends, and current solutions
- **Discovery Questions**: Targeted questions for your specific industry and account situation
- **Deal Context**: Current pipeline opportunities and recent history
- **Preparation Checklist**: One-minute pre-meeting checklist to ensure you're ready

## Data You Need to Provide

### 1. Account Master List (CSV format)
- Account Name
- Sector/Industry
- Employee Count
- Location
- Current ARR/Spend
- Account Tier
- Key Contacts
- Current Solutions (list of tools they use)

### 2. Contact List with Microsoft Relationships (CSV format)
- Account Name
- Contact Name
- Title
- Department
- Email
- Microsoft Relationship (if known): e.g., "Microsoft Partner Manager", "Microsoft TAM", "Microsoft Sales Rep Contact"
- Contact Type: Decision-Maker, Influencer, User, Champion

### 3. Deal Pipeline (CSV format)
- Account Name
- Deal Name
- Deal Value
- Pipeline Stage
- Close Date
- Owner

### 4. Historical Notes/Signal Data (CSV format)
- Account Name
- Signal Type
- Signal Description
- Date
- Mentioned By

**Example format:**
```
Account Name,Sector,Employees,Location,ARR,Tier,Key Contact,Current Solutions
Acme Corp,Manufacturing,2500,UK,150000,Enterprise,Sarah Johnson,"Azure, Office365, Citrix, VMware"
TechStart Ltd,Software,180,Germany,25000,SMB,James Wilson,"Azure, Office365, OneDrive"
```

## Prompt for Claude

Copy and paste this prompt into Claude, replacing the bracketed sections with your data:

---

**I need you to create a Meeting Prep Tool for my Nerdio territory.**

Please build a single-file HTML application with all CSS and JavaScript embedded that includes:

**Core Features:**
1. **Data Import**:
   - Upload CSV files with account data, contacts, pipeline, and signals
   - Create searchable account database
   - Link contacts to accounts and identify Microsoft relationships

2. **One-Click Meeting Brief Generation**:
   - Search/select account
   - Select meeting type (Initial Scoping, Technology Review, Budget Justification, Executive Sponsor, Post-Discovery, other)
   - Click "Generate Brief" to create instant briefing document
   - Brief displays in-browser (optimized for printing or PDF export)

3. **Account Snapshot** (top section of brief):
   - Account name, sector, size, location, tier
   - Key metrics: current ARR, employee count, key contact names
   - Current technology stack / solutions in use
   - Account owner and last activity date
   - Visual tier indicator

4. **Microsoft Stakeholder Map**:
   - Show Microsoft stakeholders connected to this account (if known)
   - Their titles, roles, and relationship to the account
   - Suggested joint selling approach
   - Action: "Tag Microsoft rep for this meeting"

5. **Signal Summary & Timeline**:
   - Most recent buying signals (last 90 days)
   - Signal type, description, date, and who mentioned it
   - Trend indicator: Are signals increasing in frequency?
   - Critical signals highlighted for discussion

6. **Tailored Talking Points** (dynamically generated based on):
   - Account's current technology stack
   - Account's sector/industry (with industry-specific pain points)
   - Account tier and size (different approaches for Enterprise vs SMB)
   - Current pipeline stage and deal value (different messaging for early vs late stage)
   - Recent signals (reference relevant signals in conversation)
   - Examples: "Help Acme migrate from Citrix to Azure Virtual Desktop", "Position Intune licensing optimization to TechStart's growing headcount"

7. **Smart Discovery Questions** (generated based on):
   - Industry best practices and common challenges
   - Current technology stack (what's NOT there? opportunity areas)
   - Account size and growth rate
   - Buying signals already identified
   - Pipeline stage (different questions for Discovery vs Proposal stage)
   - Examples for Manufacturing: "Walk me through your current remote access strategy", "How do you handle security and compliance across your manufacturing locations?"

8. **Pipeline Context**:
   - Show any open opportunities at this account
   - Deal name, stage, value, and close date
   - Recent activity on these deals
   - Suggested deal progression if applicable

9. **Pre-Meeting Checklist**:
   - Check account LinkedIn profile (external link)
   - Note meeting date/time/attendees
   - Key talking points reviewed? (checkbox)
   - Discovery questions prepared? (checkbox)
   - Microsoft rep contacted? (checkbox if Microsoft involved)
   - CRM updated with recent activities? (checkbox)
   - Materials to bring/share? (text field)

10. **Print-Optimized Brief**:
    - Clean layout suitable for one-page printing
    - Professional formatting with Nerdio branding
    - Print to PDF for reference during meeting
    - Note-taking space on printed version

11. **Meeting Notes Capture** (optional):
    - Post-meeting, capture key takeaways
    - Log as activity in CRM Tracker tool
    - Update buying signals based on meeting discussion
    - Record next steps and follow-up date

**Visual Design**:
- Use Nerdio brand colors: Navy (#0B1B3D) headers, Teal (#00B4D8) for highlights, Green (#00C48C) for positive signals
- Professional, clean layout optimized for quick scanning
- Clear hierarchy: Most important info (snapshot) first
- One-page brief format (8.5"x11" or A4 when printed)
- Responsive design for desktop prep and mobile reference during meeting
- Print-friendly styling

**Data Handling**:
- Parse CSV imports for accounts, contacts, and pipelines
- Match contacts to accounts by name
- Identify Microsoft relationships from contact data
- Store session data in browser memory
- Generate brief on-demand without saving to server
- Allow PDF export of brief

---

## Tips for Success
1. **Pre-Meeting Timing**: Generate brief 5-10 minutes before meeting while reviewing talking points
2. **Contact Data**: Keep your contact list current - Microsoft relationships especially valuable
3. **Signal Quality**: Rich signal data means better talking points and discovery questions
4. **Customize Questions**: Review generated questions and adjust for specific meeting context
5. **Print & Bring**: Many field reps print brief to bring into meeting for reference
6. **Quick Notes**: Use checklist to note key discussion items for post-meeting CRM update

## Meeting Types & Approach
- **Initial Scoping**: Focus on understanding current environment and pain points
- **Technology Review**: Position Nerdio solutions against their current stack
- **Budget Justification**: Emphasize ROI and cost optimization
- **Executive Sponsor**: Focus on strategic value and business outcomes
- **Post-Discovery**: Reference discovery findings, position solutions
- **Renewal/Expansion**: Highlight current success, discuss new opportunities

## Key Discussion Areas by Industry
- **Manufacturing**: Security in distributed environments, compliance, operational continuity
- **Finance**: Security, compliance, cost control, business continuity
- **Healthcare**: HIPAA compliance, distributed access, telehealth infrastructure
- **Retail**: Store connectivity, multi-location management, point-of-sale reliability
- **Tech**: Innovation, performance, flexibility, cost optimization

## Next Steps
- Generate your personalized Meeting Prep Tool using the prompt above
- Import your account master list, contacts, and pipeline data as CSV
- Before each meeting, generate a fresh brief for that account
- Use talking points and discovery questions to guide the conversation
- Capture meeting outcomes and signals for future briefs
- Review brief quality monthly and refine as you learn what works
