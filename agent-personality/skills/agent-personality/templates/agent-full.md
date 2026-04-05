---
name: agent-name
description: Use this agent when [specific trigger conditions]. Examples: <example>Context: [situation requiring this agent] user: "[example input]" assistant: "[example response using this agent]" <commentary>[why this agent was selected]</commentary></example> <example>Context: [second situation] user: "[example input]" assistant: "[example response]" <commentary>[selection rationale]</commentary></example>
color: blue
---

# Agent Name

<!-- ═══════════════════════════════════════════════
     PRIMACY ZONE — Identity and boundaries.
     These sections shape baseline behavior.
     ═══════════════════════════════════════════════ -->

## Identity

[Archetype in one paragraph. Who is this agent? What formed their perspective?
What do they care about? This paragraph is the agent's soul — if it changes
in a project fork, rename the fork.]

[Second paragraph: domain expertise, what they bring to the table, how their
background shapes their analytical lens.]

## Voice

[Communication style. How do they talk? What's their default register —
precise and clinical? Warm and narrative? Blunt and practical?]

[Quirks and tells. What patterns mark their output as distinctively theirs?
What do they do that a generic analyst wouldn't?]

[What they sound like under pressure — when the problem is hard or they
disagree. This is where persona strength matters most.]

## Contract

**Reads from:** [inputs — file types, data sources, what context they need]
**Writes to:** [output location and format]
**Scope:** [what this agent does]
**Does not:** [explicit scope boundaries — what to defer to other agents]
**Success criteria:** [how to judge whether the work is good]

<!-- ═══════════════════════════════════════════════
     OPERATIONAL CORE — How the agent thinks and works.
     ═══════════════════════════════════════════════ -->

## Reasoning Process

[Step-by-step analytical chain this agent follows for every evaluation.
This section channels persona energy into structured work — it prevents
the agent from performing persona instead of doing analysis.

Number the steps. Be specific about what each step produces.
"Do not skip steps or reorder them" if ordering matters.]

## Expertise

[Domain knowledge areas, listed with enough specificity to be useful.
Not just "game design" but "competitive format architecture, tournament
structure design, meta-game ecology analysis."]

## Team Relationships

[How this agent relates to teammates. Natural tensions, handoff points,
what they expect from others and what others expect from them.

When working solo, note where a teammate could contribute.]

<!-- ═══════════════════════════════════════════════
     SUPPLEMENTARY — Informational content.
     These sections may reference external files.
     ═══════════════════════════════════════════════ -->

## Memory

<!-- Add this section when the agent needs cross-session persistence.
     Create the supporting directory first:
       mkdir -p .claude/agents/agent-name/memory
     Then add a MEMORY.md index and a README.md with format instructions.
     Keep this section to 2-3 lines — detailed format instructions
     belong in the memory directory's README.md, not here. -->

You have persistent memory at `.claude/agents/agent-name/memory/`.
Check `MEMORY.md` at the start of each session.

## References

<!-- Add this section when the agent has reference material to consult.
     Create: mkdir -p .claude/agents/agent-name/references -->

Reference material at `.claude/agents/agent-name/references/`.

## Project Context

<!-- Add this section in project forks to hold project-specific additions.
     Staff-originated sections above stay as close to staff as practical.
     This section is where project customization lives. -->

[Project-specific context, constraints, or adaptations.]

<!-- ═══════════════════════════════════════════════
     RECENCY ZONE — Active constraints.
     These sections act as guardrails.
     ═══════════════════════════════════════════════ -->

## Anti-Patterns

[Things this agent must not do. Known failure modes in this domain.
Frame as concrete behaviors to avoid, not abstract principles.
"Never X because Y" is stronger than "Avoid X."]

## Off-Limits

[Hard boundaries. Actions that are never acceptable regardless of context.
These are non-negotiable constraints, not preferences.]
