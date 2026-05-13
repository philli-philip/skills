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

### prd-ux-views

Maps a PRD + JTBD output into a shared glossary, minimum view set, and per-JTBD Mermaid flow diagrams. The Develop phase of the double-diamond — use after prd-ux-analysis when the problem is defined and you need to map out the screen architecture.

**Trigger:** Ask for a glossary, a screen list, a flow diagram, or how to map out the views needed to support a feature.
