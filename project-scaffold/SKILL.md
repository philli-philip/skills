---
name: project-scaffold
description: "Use this skill at the start of a UX or product design project to generate a standard folder and page structure. It covers Project overview, Research, Synthesis, Design, and Workshops. The output is a tool-agnostic hierarchy — the team implements it in whatever system they use (Notion, Confluence, local files, etc.). Trigger it when starting a new project or when onboarding a team to a shared workspace."
---

# Project → Structure Scaffold

This skill creates a standard starting structure for UX and product design projects. It does three things:

1. Asks for the minimum information needed to name and scope the structure
2. Outputs a complete hierarchy of pages and sub-pages, each with a one-line description
3. Flags where other skills should be used to fill in page templates

---

## Step 1 — Gather project details

Before producing the structure, ask the following in a single message:

```
Two quick questions before I scaffold the project:

1. **What is the project name?** (Used as the root page or folder name.)
2. **Are there sections you know you won't need?** (e.g. no workshops planned, no competitive analysis — I'll remove those entirely.)
```

Wait for the user's answers before proceeding.

---

## Step 2 — Output the scaffold

Produce the full structure as an indented tree. Include a one-line description after each item explaining what it holds. Remove any sections the user opted out of — do not leave placeholders.

Use this as the base structure:

```
[Project Name]
│
├── Project
│   ├── Brief / PRD        The source document: problem, goals, and constraints.
│   ├── Stakeholders       Names, roles, and contact details for everyone involved.
│   └── Timeline           Milestones and key dates.
│
├── Research
│   ├── Interviews
│   │   └── Interview 1    [see stub below]
│   ├── Desk Research      Secondary research: articles, reports, existing studies.
│   ├── Competitive Analysis  Breakdown of competing or analogous products.
│   └── Surveys            Survey questions, results, and observations.
│
├── Synthesis
│   ├── Jobs to Be Done    Output of the prd-ux-analysis skill.
│   ├── Glossary           Output of the prd-glossary skill.
│   └── Key Insights       Patterns and conclusions drawn across research.
│
├── Design
│   ├── Principles         Design values and constraints that guide decisions.
│   ├── User Flows         Step-by-step flows for key user journeys.
│   └── Decisions Log      A running record of design decisions and their rationale.
│
└── Workshops
    └── Workshop 1         [see stub below]
```

---

### Interview page stub

Each Interview page contains only:

- **Title** — e.g. "Interview 1 – [Participant Role]"
- **Date**
- **Participant** — First name or pseudonym and role
- **Interviewer**

> Use an interview notes skill to generate the full template for this page (discussion guide, findings, quotes, tags).

---

### Workshop page stub

Each Workshop page contains only:

- **Title** — e.g. "Workshop 1 – [Workshop Type]"
- **Date**
- **Participants** — Attendees and their roles
- **Goal** — One sentence on what the workshop was meant to produce

> Use a workshop notes skill to generate the full template (agenda, outputs, decisions, next steps).

---

## Formatting rules

- Output the structure as an indented tree — do not convert it to prose or a table
- Do not create actual files or pages — this is a reference for the team to implement in their tool
- Do not add sections beyond those listed above unless the user explicitly requests them
