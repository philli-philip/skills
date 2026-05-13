---
name: prd-glossary
description: "Use this skill when you have a PRD and optionally a JTBD analysis and need to establish a shared domain vocabulary before design begins. It scans both documents for essential nouns, filters out UI terms and generic software terms, flags terminology inconsistencies with a canonical recommendation, and sorts the result from the most foundational concepts to the most specific. Trigger it after running prd-ux-analysis, or any time a user asks for a glossary, a term list, or wants to align the team on what words mean before design or development starts."
---

# PRD → Domain Glossary

This skill extracts a shared vocabulary from a PRD and JTBD analysis. It does three things:

1. Filters the documents down to **essential domain and product nouns only** — no UI terms, no generic software terms, no verbs
2. Flags **terminology inconsistencies** and recommends a canonical term for each
3. Sorts the glossary **foundational terms first**, so readers build understanding in the right order

---

## Step 1 — Confirm inputs

Before doing anything, ask:

```
To build the glossary I'll need:

1. **The PRD** — do you have it ready to share, or has it already been shared in this conversation?
2. **The JTBD analysis** — if you've run prd-ux-analysis, paste the Jobs to be Done output here. If you don't have it, I can still produce a glossary from the PRD alone, but it will be less complete.
```

Wait for the user's response before proceeding to Step 2.

---

## Step 2 — Extract candidate terms

Read both documents carefully. Collect every noun that:

- Appears **more than once** across the PRD and JTBD combined, AND
- Is **essential to understanding** a job to be done or a product requirement — removing it would make a sentence ambiguous or meaningless

**Drop anything that is:**
- A UI element — button, modal, form, screen, page, tab, sidebar, dropdown, field
- A generic software or engineering term — API, database, system, service, endpoint, user, data, workflow, integration, platform, backend, frontend, infrastructure
- A verb or action — even if nominalized (e.g., "submission", "validation", "processing")
- A term that appears only once and is not load-bearing for any JTBD

Do not guess at terms that aren't in the source documents.

---

## Step 3 — Detect inconsistencies

Before writing definitions, scan for the same concept referred to by different names or with shifting meaning. Common patterns:

- Two synonyms used interchangeably (e.g., "contract" and "agreement")
- A term used with different scope in different sections (e.g., "customer" meaning end-user in one section and account in another)
- An abbreviation used before or without its full form

For each inconsistency found, decide on the canonical term. Prefer the term that is more precise, more specific to the domain, or used more frequently. You will flag this inline in the glossary entry.

---

## Step 4 — Produce the glossary

Write the glossary as a flat list, sorted from most foundational to most specific. A foundational term is one that other terms depend on to be understood — define it first.

Format each entry as:

**Term**
One concise sentence definition drawn from what the PRD and JTBD actually say. Do not invent meaning beyond the source. If the PRD never defines the term but uses it, extrapolate only what is directly implied and mark it.

If there is a terminology inconsistency, add it on the next line:
> Also called "[other term]" — use **Term** as the canonical name going forward.

If the definition cannot be inferred from the source documents:
> ⚠️ Definition not specified in PRD — confirm with the product owner before design begins.

---

## Formatting rules

- Bold each term name as its own line — no bullet points, no numbering
- One sentence per definition — expand only if a term is genuinely ambiguous without more context
- Do not include section headers inside the glossary — it is a flat list
- Do not include terms that are not found in the source documents
- Do not include UI or software terms even if the user asks — explain why if challenged
