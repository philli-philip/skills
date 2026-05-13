# Philip's Agent Skills

A collection of agent skills for Claude Code and other AI agents.

## Install

```bash
npx skills add philli-philip/skills
```

Or install a specific skill:

```bash
npx skills add philli-philip/skills --skill prd-ux-analysis
```

## Skills

### prd-ux-analysis

Reviews a PRD from the perspective of a senior UX designer using the double-diamond model (Discover → Define phase). Extracts Jobs to be Done, surfaces UX gaps and open questions, flags assumption risks, and produces a team-ready briefing before design begins.

**Trigger:** Share a PRD and ask for UX feedback, a design review, or what's missing before design starts.

### prd-glossary

Extracts a domain glossary from a PRD and JTBD analysis. Filters to essential nouns only, flags inconsistent terminology, and sorts terms from most foundational to most specific.

**Trigger:** After running `prd-ux-analysis` (or when you have a PRD and want a shared vocabulary before design begins).
