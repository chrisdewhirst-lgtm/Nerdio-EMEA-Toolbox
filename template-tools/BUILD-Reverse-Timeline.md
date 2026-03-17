# BUILD: Reverse Timeline Tool

## Purpose
Works backward from a target close date to map every milestone and action required to win the deal on schedule. Ensures nothing falls through the cracks and keeps complex deals moving forward.

## What This Tool Does
- **Reverse Milestone Mapping**: Input target close date; tool calculates when each sales phase must be completed
- **Action Planning**: For each milestone, define specific actions, owners, and due dates
- **Stage Durations**: Reference typical sales cycle lengths (Discovery 3-4 weeks, Qualification 2-3 weeks, etc.)
- **Dependency Tracking**: Identify which milestones must happen before others can begin
- **Progress Dashboard**: Visual timeline showing planned vs. actual milestone completion
- **Risk Alerts**: Flag if milestones are falling behind schedule
- **Deal Acceleration Options**: Show what can be done in parallel to compress timeline
- **Stakeholder Alignment**: Ensure all team members know their roles and deadlines

## Data You Need to Provide

### 1. Deal Details
- Deal Name
- Account Name
- Deal Value
- Current Stage
- Target Close Date
- Expected Sales Cycle Length (typical days from first meeting to close)
- Key Stakeholders & Their Roles

### 2. Sales Cycle Definition (standard or custom)
For your organization, typical durations for each stage:
- Discovery: 3-4 weeks
- Qualification: 2-3 weeks
- Proposal: 1-3 weeks
- Negotiation: 2-4 weeks

Or if you prefer to define custom phases:
- Phase 1, Phase 2, Phase 3, etc. with durations

**Example context:**
```
Deal: Acme DaaS Migration
Account: Acme Corp
Value: 250,000 EUR
Current Stage: Qualification
Target Close: 2026-05-15
Sales Cycle: 12 weeks typical
```

## Prompt for Claude

Copy and paste this prompt into Claude, replacing the bracketed sections with your data:

---

**I need you to create a Reverse Timeline Tool for complex deal planning.**

Please build a single-file HTML application with all CSS and JavaScript embedded that includes:

**Core Features:**
1. **Data Input Interface**:
   - Deal information form:
     - Deal name, account name, deal value
     - Current date / current stage
     - Target close date (the date you want to close)
     - Sales cycle length (standard: 12 weeks) or custom phases
   - Define stakeholder roles (Champion, Economic Buyer, Technical Buyer, Executive Sponsor, etc.)

2. **Reverse Timeline Calculation**:
   - User inputs target close date
   - Tool works BACKWARD to calculate when each stage must complete
   - Example: If close is May 15 and Negotiation takes 3 weeks, then:
     - Negotiation must start by April 24
     - Proposal must end by April 23
     - Proposal should start by April 2 (if 3 weeks)
     - Qualification must end by April 1
     - Qualification should start 3 weeks before that
     - Discovery must start early enough to end before Qualification begins
   - Display as visual timeline showing target dates for each phase

3. **Phase/Stage Milestone View**:
   - For each sales phase, show:
     - Phase name (Discovery, Qualification, Proposal, Negotiation, Close)
     - Target start date (calculated working backward)
     - Target completion date (milestone deadline)
     - Days remaining in phase (if phase is in progress)
     - Phase status: Not Started, In Progress, On Track, At Risk, Complete
   - Visual progress bar for each phase
   - Days elapsed vs. planned duration for current phase

4. **Milestone Definitions & Actions**:
   - For each phase, define key milestones that must be achieved:
     - Discovery: Pain discovery meeting, Current state documentation, Stakeholder identification
     - Qualification: Need assessment, ROI discussion, Decision criteria review, Champion identified
     - Proposal: Solution designed, Proposal drafted, Proposal presented, Budget confirmed
     - Negotiation: Contract review, Terms negotiation, Executive approval, Signature
     - Close: Final documentation, license activation, go-live planning
   - For each milestone, user can add:
     - Specific action (e.g., "Schedule pain discovery call with CFO")
     - Owner (who is responsible)
     - Due date (auto-calculated or manual override)
     - Description/notes
     - Dependency (must complete before this milestone)
     - Status: Not Started, In Progress, Complete

5. **Action Tracking**:
   - Master action list organized by:
     - Due date (soonest first)
     - Owner (who is responsible)
     - Milestone it's related to
     - Status (todo, in progress, complete, blocked)
   - Allow custom actions beyond standard templates
   - Assign owners and due dates
   - Track completion

6. **Timeline Visualization**:
   - Horizontal timeline showing:
     - Today's date (current position)
     - Each phase with start/end dates
     - Target close date (end of negotiation)
     - Milestone markers on timeline
     - Progress indicator showing how far through deal you are
   - Color coding: Green (on track), Yellow (at risk), Red (behind)
   - Show "weeks remaining" until close date

7. **Risk & Acceleration Analysis**:
   - Identify risks to hitting close date:
     - "Negotiation phase ends in 28 days; typical is 21 days - buffer only 1 week"
     - "Proposal not started; should start within 5 days"
     - "Key stakeholder hasn't been identified yet (needed for qual completion)"
   - Suggest accelerators:
     - "Run discovery and qualification in parallel with champion (compress by 1 week)"
     - "Request preliminary budget approval early (eliminate 1 week negotiation)"
     - "Have proposal template ready to present immediately after qualification"
   - Calculate impact on timeline if accelerators used

8. **Stakeholder Alignment View**:
   - Show each stakeholder's role and their key involvement points
   - Who needs to participate in which milestones
   - When to involve each stakeholder (too early = turf concerns, too late = no time)
   - Action items assigned to specific stakeholders
   - Help ensure everyone is aligned on timeline

9. **Deal Progression Status**:
   - Visual summary:
     - Current stage and milestone
     - Milestone completion %
     - Days elapsed vs. planned in current phase
     - Days remaining until target close
     - On Track / At Risk / Behind flag
   - If behind, show projected close date and gap vs. target
   - Show what would need to happen to get back on track

10. **Weekly Check-In Template**:
    - Generate weekly status check:
      - This week's critical milestones (what must be achieved?)
      - This week's key actions (who is doing what?)
      - Risks to timeline (what could derail us?)
      - Accelerators being pursued (how are we trying to compress timeline?)
      - Next week's priorities

11. **Collaboration Tools**:
    - Print timeline to share with stakeholders
    - Export timeline as PDF
    - Email stakeholder summary (their roles, their deadlines)
    - Generate deal brief with reverse timeline for team alignment

12. **Reporting**:
    - Timeline status report (on track, at risk, behind)
    - Action item summary by owner
    - Milestone completion history
    - Deal acceleration opportunities identified

**Visual Design**:
- Use Nerdio brand colors: Navy (#0B1B3D) for headers, Teal (#00B4D8) for milestones, Green (#00C48C) for on-track, Red (#FF6B6B) for at-risk
- Clear timeline visualization (Gantt-style or horizontal timeline)
- Phase blocks showing dates and progress
- Large milestone markers with status indicators
- "Today" marker clearly visible on timeline
- Countdown to close date prominent
- Responsive design for desktop viewing and printing

**Data Handling**:
- Calculate timeline working backward from close date
- Auto-calculate milestone dates based on typical phase durations
- Allow manual override of dates if needed
- Timestamp action completions
- Store timeline in browser memory (no external API)
- Export timeline and actions as PDF or CSV

---

## Tips for Success
1. **Be Realistic on Cycle Time**: Use actual historical data on how long your phases take, not optimistic estimates
2. **Include Buffers**: Build in 1-2 weeks of slack in each phase for unexpected delays
3. **Start Early**: If you're already in Proposal stage, there's less flexibility - adjust close date or accelerate
4. **Parallel Workstreams**: Identify what can happen in parallel (run technical eval while financial team reviews ROI)
5. **Owner Clarity**: Assign clear owners for each action; ambiguous ownership = missed deadlines
6. **Weekly Review**: Review timeline each week; if milestone missed, recalculate and adjust close date

## Sales Cycle Reality Check
- **Fast Sales Cycle** (6-8 weeks): Small deals, known decision-makers, off-the-shelf solution
- **Normal Sales Cycle** (12-16 weeks): Mid-market, multiple stakeholders, some customization
- **Long Sales Cycle** (20+ weeks): Enterprise, complex approval processes, significant integration
- **Add Time For**: Approval processes, budget cycles, competing initiatives, summer holidays

## Milestone Checklist by Phase
**Discovery** (must have before moving to Qualification):
- Pain discovery call completed with key stakeholders
- Current state/environment documented
- Business impact quantified
- Key decision-makers and influencers identified

**Qualification** (must have before moving to Proposal):
- Formal needs assessment completed
- ROI framework agreed
- Decision criteria documented and prioritized
- Internal champion identified and aligned

**Proposal** (must have before moving to Negotiation):
- Solution designed to meet their needs
- Proposal drafted and reviewed internally
- Proposal presented and client feedback captured
- Budget authorization initiated

**Negotiation** (must have before Close):
- Contract terms reviewed and issues identified
- Executive sponsors aligned on terms
- Legal review completed
- Signature authority identified and ready

## Next Steps
- Generate your personalized Reverse Timeline Tool using the prompt above
- For your current largest deal, input the target close date
- Let the tool calculate what must happen and when
- Share timeline with your team to align on milestones
- Track action completion weekly
- Adjust timeline if milestones slip (don't ignore slippage)
- Use acceleration strategies to compress timeline if needed
