---
name: prd-ux-views
description: "Use this skill after prd-ux-analysis, when the JTBD are defined and you need to move into the Develop phase of the double-diamond. It takes a PRD and an optional JTBD table and produces outputs: a glossary of domain terms, a minimum set of views that covers each JTBD, and per-JTBD Mermaid flow diagrams combined into a single whole-flow diagram. Trigger it when a user asks for a glossary, screen list, flow diagram, or wants to map out the views needed to support a feature."
---

# PRD → Glossary, Views & Flows (Define → Develop)

This skill bridges the gap between a problem definition and a design-ready view architecture. It does three things:

1. Builds a **Glossary** of domain terms so the whole team uses the same language
2. Maps the **minimum set of views** (screens) needed to support every Job to be Done
3. Produces **Mermaid flow diagrams** — one per JTBD, then a combined diagram that shows the whole flow

All three outputs are coupled: glossary terms appear as view names; view names appear as nodes in the flow diagrams. Consistency is the point.

---

## Step 1 — Ask one scoping question

Before producing any output, ask this single question. Do not analyze yet.

```
Quick questions before I start:

1. Are there existing screens or application that the system must fit into?
(At this point every screen is just a placeholder, how the view looks, will come later)
If yes, describe them briefly. If no, I'll propose the minimum view set from scratch.

2. Should I work on Glossary, Views and flows at the same time, or should we start with the Glossary first?

```

Also confirm whether the user has a JTBD table from the prd-ux-analysis skill. If not, derive it inline from the PRD before producing any output.

Wait for the user's answer before proceeding to Step 2.

---

## Step 2 — Produce all three sections

With the PRD, JTBD table, and scoping answer in hand, produce all three sections in a single response.

---

### Section 1: Glossary

Scan the PRD and JTBD table for **domain nouns** — entities, roles, statuses, and actions that recur or are load-bearing for a JTBD. Define each one.

**Format:**

**Term** — 1—2 sentence plain-language definition. Written so a new team member or people joining the project can get up to speed.

**Rules:**
- Include nouns only if it appears more than once AND is essential to understanding a JTBD or the PRD
- Do not include UI terms (button, modal, form, screen) — only domain and product terms
- If the PRD uses a term inconsistently, call it out and pick the canonical definition
- Sort by the most important or foundational terms first
- Exclude terms that are common in software development OR are actions/verbs

---

### Section 2: Views

Map the **minimum set of views** (screens or surfaces) needed to cover every step of every JTBD. Fewer views is better — a view that serves three JTBDs is better than three views that each serve one. Large forms might be split into multiple views.

**Format:**

1. **View Name** — One-sentence purpose. Serves: JTBD 1, JTBD 3.

**Rules:**
- Use exact terms from Section 1 in view names and descriptions
- When one view serves multiple JTBDs, say so explicitly
- When a step could be a modal or drawer instead of a full screen, flag it: *(can be modal — reduces step count)*
- Do not specify layout, component choices, or visual detail — only purpose and scope
- Every view listed here must appear in Section 3

---

### Section 3: Flow Diagrams

Produce a Mermaid flow diagram for each JTBD, then a combined diagram that overlays all flows.

**Per-JTBD diagram rules:**
- Use `flowchart LR`
- Node labels must use exact View Names from Section 2
- Start every flow with a `Start([Start])` node; end with `Done([Done])`
- Label every edge with the user action or system transition that causes the move
- Use diamond nodes `{Decision}` for branch points, error states, or conditional paths
- Use subgraphs `subgraph` to group related views together

**Format for each:**

```
#### Flow: [JTBD short name]

[one-sentence description of the job this flow covers]

flowchart LR
    Start([Start]) -->|triggers flow| ViewA[View Name]
    ...
    Done([Done])
```

**Combined diagram rules:**
- After all individual flows, produce one `flowchart LR` that contains all nodes and edges
- Each view node appears only once — shared views are the same node
- Use `classDef` to colour-code flows by JTBD (one colour per JTBD)
- Assign each node to its JTBD class: `class ViewA jtbd1`
- Where a view is shared across JTBDs, assign it to a `shared` class instead
- Label edges with both the action and the JTBD abbreviation (e.g., `|submit J1|`) when the same edge would otherwise be ambiguous

**Format:**

```
#### Combined Flow
lu
flowchart LR
    classDef jtbd1 fill:#DBEAFE,stroke:#3B82F6
    classDef jtbd2 fill:#D1FAE5,stroke:#10B981
    classDef shared fill:#F3F4F6,stroke:#6B7280

    Start([Start])
    ...
    Done([Done])

    class ViewA jtbd1
    class ViewB shared
```

---

## Formatting rules

- Use headers exactly as shown above
- Bold key terms; don't bold everything
- Glossary terms must appear verbatim in view names and flow node labels
- Do not produce wireframes, UI layout suggestions, or component recommendations — that belongs to another skill
- Do not repeat the PRD back to the user — produce outputs only
