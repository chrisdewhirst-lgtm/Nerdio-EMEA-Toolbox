# BUILD: CRM Tracker Tool

## Purpose
Lightweight, mobile-friendly CRM for tracking TPID (Third-Party ID) relationships, buying signals, engagement notes, and activity logging. Perfect for quick updates between CRM syncs or for real-time meeting notes.

## What This Tool Does
- **Account Management**: Search and view all accounts with contact hierarchy
- **TPID Tracking**: Track relationships with key decision-makers, influencers, and users at each account
- **Signal Logging**: Record and timestamp buying signals (tech investments, organizational changes, budget indicators)
- **Activity Journal**: Quick-log meetings, calls, emails with notes and outcomes
- **Contact Hierarchy**: Visualize org structure and contact relationships
- **Notes & History**: Full activity trail per account and contact
- **Quick Actions**: Log activity in seconds without leaving the tool
- **Export**: Generate CRM summary or activity reports

## Data You Need to Provide

### 1. Account Master List (CSV format)
- Account Name
- Account ID (optional, for CRM reference)
- Sector/Industry
- Employee Count
- Location (Country/City)
- Current Account Owner
- Account Tier (Enterprise, Mid-Market, SMB)

### 2. Contacts/Hierarchy (CSV format)
- Account Name
- Contact Name
- Job Title
- Department
- Contact Type (Decision-Maker, Influencer, User, Economic Buyer, Technical Buyer, Champion)
- Email (optional)
- Phone (optional)
- Primary Contact? (Yes/No)
- Contact Tier/Level (C-Suite, Director, Manager, User)

### 3. CRM Export (optional)
- Full CRM export (Salesforce, HubSpot, Pipedrive) with accounts, contacts, and opportunities

**Example format:**
```
Account Name,Contact Name,Title,Department,Contact Type,Tier
Acme Corp,Sarah Johnson,VP IT,IT Operations,Decision-Maker,Director
Acme Corp,Mike Chen,IT Manager,IT Operations,Technical Buyer,Manager
TechStart Ltd,James Wilson,Head of Engineering,Product,Champion,Director
```

## Prompt for Claude

Copy and paste this prompt into Claude, replacing the bracketed sections with your data:

---

**I need you to create a CRM Tracker Tool for my Nerdio territory.**

Please build a single-file HTML application with all CSS and JavaScript embedded that includes:

**Core Features:**
1. **Data Import**:
   - Upload CSV files for accounts, contacts, and opportunities
   - Import structure: Account Name, Contact Name, Title, Department, Contact Type, Tier, Email, Phone
   - Parse and validate contact hierarchy
   - Create searchable account/contact database

2. **Account Dashboard**:
   - Search bar to quickly find accounts
   - Account card showing: name, tier, sector, employee count, location, owner, contact count
   - Quick stats: total contacts, contact types distribution, last activity date
   - List of all related contacts with their titles and types
   - Contact hierarchy visualization (org chart view, optional)

3. **TPID Tracking**:
   - View all contacts per account with relationship status
   - Contact roles: Decision-Maker, Influencer, User, Economic Buyer, Technical Buyer, Champion
   - Relationship strength indicator (new, established, warm, cold)
   - Contact frequency score (how often have you interacted?)
   - Relationship timeline (when did you first meet this contact?)
   - Flag key relationships (star/favorite contacts)

4. **Signals Logging Interface**:
   - Quick-log interface to record buying signals:
     - Signal Type: Technology Investment, Organizational Change, Budget Indicator, Competitive Activity, Growth Signal, Pain Point Mentioned
     - Signal Description (free text)
     - Mentioned By (contact name)
     - Signal Date
     - Signal Strength (High/Medium/Low)
     - Required Action (optional)
   - Timestamp automatically
   - Signals tied to specific contacts and accounts
   - Signal history searchable and sortable by date/type/strength

5. **Activity Logging**:
   - Quick-log button for rapid activity entry:
     - Activity Type: Meeting, Call, Email, Demo, Proposal, Content Share, Other
     - Account & Contact (searchable dropdown)
     - Activity Date & Time
     - Duration
     - Attendees
     - Outcome (positive, neutral, negative, pending)
     - Key Takeaways (text notes)
     - Next Steps
   - Auto-timestamp entries
   - Activity appears immediately in account timeline

6. **Account Timeline View**:
   - Chronological view of all activities and signals for each account
   - Mixed view showing meetings, calls, signals, and milestone events
   - Filter by activity type or contact
   - Show time elapsed since last activity
   - Highlight recent activities and signals

7. **Contact Notes & Profiles**:
   - Individual contact profile page:
     - Contact details (name, title, department, email, phone)
     - Relationship timeline (how long have you known them)
     - Activities involving this contact
     - Signals they've mentioned
     - Contact preferences/notes
     - Last interaction date and type
     - Custom notes field for personal insights

8. **Smart Actions & Reminders**:
   - Identify contacts not contacted in 30+ days
   - Highlight warm signals waiting for follow-up
   - Suggest next actions based on signal strength and deal stage
   - Show accounts ready for next engagement level

9. **Reporting & Export**:
   - Generate activity summary (date range, contact, activity type)
   - Export account intelligence brief (all signals + activities for an account)
   - Export contact list with last interaction dates
   - Generate outreach recommendations

**Visual Design**:
- Use Nerdio brand colors: Navy (#0B1B3D) headers, Teal (#00B4D8) for action buttons, Green (#00C48C) for positive signals, White (#FFFFFF) backgrounds
- Clean, card-based layout
- Mobile-first responsive design (works great on phone for field notes)
- Large touch targets for quick mobile interaction
- Timeline view with visual indicators for activity types
- Color-coded signal types for quick scanning

**Data Handling**:
- Store all data in browser memory (no external API)
- Allow local export/import to preserve data between sessions
- Validate all inputs
- Timestamp all entries automatically
- Handle missing contact information gracefully

---

## Tips for Success
1. **Mobile Use**: Access this on your phone/tablet during and after meetings for quick note capture
2. **TPID Structure**: Assign contact types clearly - Decision-Makers and Champions are priority
3. **Signal Quality**: Be specific - "Budget approved for cloud migration" beats "mentioned budget"
4. **Activity Detail**: Include outcome and next steps so you know where deals stand without checking CRM
5. **Contact Updates**: Sync contact data from your CRM monthly to keep hierarchy current
6. **Export Regularly**: Download your activity log weekly as backup and for CRM sync

## Signal Types to Track
- **Technology**: New cloud migration, Microsoft investments, infrastructure changes
- **Organizational**: New exec hires, department restructuring, role changes
- **Budget**: Budget cycles starting, approved spend, purchasing timelines
- **Competitive**: Competitive losses, competing solution evaluations
- **Growth**: Expansion plans, new office openings, headcount growth
- **Pain**: Problems with current vendor, tech debt, security concerns

## Next Steps
- Generate your personalized CRM Tracker using the prompt above
- Import your account master list and contact hierarchy as CSV
- Start logging activities and signals from today forward
- Review your signal log weekly to prioritize outreach
- Export activity summaries monthly for CRM sync and territory reviews
