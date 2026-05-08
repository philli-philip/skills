---
name: prd-ux-analysis
description: "Use this skill whenever you have a PRD, product brief, or feature spec that needs a UX design review before work begins. It analyses the document through the lens of a senior UX designer using the double-diamond model — specifically the Discover and Define phases. It extracts Jobs to be Done, surfaces UX gaps and open questions, flags assumption risks, and produces a team-ready briefing on what needs to happen before design can start. Trigger it when a user shares a PRD and asks for feedback, a design review, UX gaps, or wants to know what's missing before the design phase."
---
 
# PRD → UX Analysis (Discover → Define)
 
This skill helps translate a PRD — often messy, incomplete, or written from a product/engineering lens — into a clear UX foundation. It does three things:
 
1. Extracts and reframes **Jobs to be Done** from the PRD text
2. Identifies **UX gaps and open questions** that must be resolved before design begins
3. Produces a **design process alignment** summary so the team understands what comes next and why
---
 
## Step 1 — Ask before you analyze
 
Before producing any output, ask the following questions. Keep it to one message. Do not analyze the PRD yet.
 
```
Before I dig in, a few quick questions:
 
1. **How thorough can the Discover and Define phase be?** (e.g., is there time and budget for research, or do we need to work with what's already known?)
2. **Is there usage data as a starting point?** (e.g., analytics, support tickets, sales call notes, existing product telemetry)
3. **Are there known constraints or implicit expectations?** (e.g., existing design system, platform, deadlines, stakeholder assumptions that aren't written down)
```
 
Wait for the user's answers before proceeding to Step 2.
 
---
 
## Step 2 — Analyze the PRD
 
With the PRD and the user's answers in hand, produce the full analysis. Structure it as follows:
 
### Section 1: Jobs to be Done
 
Extract the implicit and explicit user goals from the PRD and put them into a table.
 
| User | Situation | Need | Goal | Source |
| --- | --- | --- | --- | ---- |
| As Back-office worker | when assigned a ticket to send a contract to the customer | I want to have the contract automatically generated | so that I can not make any mistakes and forward it to DocuSign or send it via E-Mail | Explicit |
 
There can be any number of JTBD. Do not invent goals that have no basis in the PRD — mark gaps instead.
 
**Prompt yourself:** Who is actually doing the work? Who benefits? Are there secondary users whose JTBDs are being ignored? What where steps the user had to go through before and steps that might be in the real world?
 
---
 
### Section 2: UX Gaps & Open Questions
 
List what is unclear, missing, or undecided from a user experience perspective. Be specific — reference actual language from the PRD where possible.
 
Group by type:
 
- **User clarity gaps** — things we don't know about who the user is or how they think
- **Flow gaps** — missing steps, edge cases, how flows start and end.
- **Decision gaps** — choices in the PRD that need a UX opinion (e.g., "can reps edit contracts?" should be answered from a user trust / error prevention lens, not just a policy lens)
- **Assumption risks** — statements in the PRD that assume user behavior without evidence
Do not soften these. If the PRD is vague or contradictory, say so directly.
 
---
 
### Section 3: Clarifications Needed
 
Based on the gaps above, list the specific things that should be looked at in more detail. This is part of the PRD process.
 
Format each item as a research question:
> "We need to understand whether users [X] in order to decide [Y]."
 
Mark each as:
- 🔴 **Critical** — Hypothesis about user behaviour that are important for the success of the product. Mostly the core assumptions of the feature. 
- 🟡 **Important** — would significantly affect the design direction
- 🟢 **Nice to have** — would improve confidence but design can move forward
---
 
### Section 4: Design Process Alignment
 
Write a short briefing (3–5 sentences) for the team that explains:
 
- What phase of work this is (Discover → Define — we are NOT designing yet)
- What the output of this phase is (a clear problem definition, not a solution)
- What comes next and what triggers the move to the next phase
- Any risks of skipping or rushing this phase given what's in the PRD
This section is written to be read aloud or shared directly with a team. Keep it plain, concrete, and non-jargony. Make it clear what needs to be done to close the phase and start the next phase.
 
---
 
## Formatting rules
 
- Use headers exactly as shown above
- Bold key terms; don't bold everything
- Do not produce wireframes, flows, or UI suggestions — that belongs to the another skill
