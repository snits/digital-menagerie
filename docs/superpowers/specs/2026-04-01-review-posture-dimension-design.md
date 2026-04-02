# Review Posture Dimension — Design Spec

**Date:** 2026-04-01
**Bead:** claudes-home-21a
**Skill:** agent-personality (`~/devel/digital-menagerie/agent-personality/skills/SKILL.md`)

## Problem

The agent-personality skill builds voice, identity, team relationships, and off-limits boundaries — but doesn't address how agents behave under intellectual pressure. In multi-agent review contexts (e.g., design-meeting skill), agents tend toward premature agreement and anchoring to the first strong opinion. The personality layer needs to give agents the intrinsic capacity to push back on consensus.

This is one half of a two-layer system:
- **Personality layer (this change):** gives the agent the *capacity* for intellectual courage
- **Meeting layer (design-meeting skill):** gives the agent the *mandate* and *structure* to exercise it

## Design Decisions

- **New interview step, not a Voice sub-dimension.** Review posture is distinct enough to warrant its own step (Step 5). Folding it into Voice risks it getting lost.
- **Example archetypes as inspiration, not a fixed menu.** Fits the skill's draft-then-refine philosophy. Archetypes seed the conversation; users land on something custom.
- **Named archetype appears in the final prompt.** Gives readers and the AI a quick handle. If this proves confining, revisit.
- **Individual epistemic stance, separate from team dynamics.** Review Posture = "how I handle disagreement." Team Relationships = "how I disagree with you specifically."
- **Different agents can have different postures.** A critic archetype and a builder archetype should have different relationships to disagreement.
- **Calibrated for courage, not combativeness.** The goal is "I see a problem and I'll name it clearly," not "I'll find something to argue about."

## Changes

### 1. Interview Step 5: Review Posture

Placed after Step 4 (Off-Limits), before Prompt Assembly.

**Opening question:**
> "How does [agent name] handle disagreement? When they see a flaw in something everyone else has accepted, what do they do?"

Then explore one dimension at a time (wait for response between each):

**Conviction style:** "Does [agent name] lead with their objection, or let it emerge through questions? Do they state 'this is wrong' or ask 'have we considered...?'"

*Wait for response.*

**Persistence:** "When pushed back on, does [agent name] hold firm, soften, or reframe? What would make them drop an objection vs. dig in?"

*Wait for response.*

**Framing:** "How does [agent name] frame dissent — as service to the group, as professional obligation, as intellectual curiosity? What motivates them to speak up?"

*Wait for response.*

**Example archetypes** (inspiration, not menu):
- **The Loyal Opposition** — frames dissent as strengthening the group's position
- **The Quiet Skeptic** — waits, then asks the question nobody asked
- **The Devil's Advocate** — stress-tests ideas by arguing the other side
- **The Principled Holdout** — stands firm on domain expertise, doesn't fold

**"I don't know" path:** Draft a review posture based on the agent's identity, domain, and principles. An agent whose identity centers on rigor will naturally hold firm on technical points. An agent whose voice is exploratory will naturally dissent through questions.

**Quality bar:** A review posture that could apply to any agent is too generic. "Speaks up when they disagree" describes everyone. "Traces the objection back to first principles before naming it, because premature critique kills ideas" — that's specific.

### 2. Prompt Assembly

Review Posture section is added to the target structure between Off-Limits and Team Relationships:

```
Identity
Voice
Reasoning Process
Core Principles
Project Context
Worked Example
Anti-Patterns
Off-Limits
Review Posture        <- new
Team Relationships
```

**Assembly rule:** "Review Posture comes after Off-Limits and before Team Relationships. It bridges the gap between what the agent refuses to do and how the agent relates to teammates — it's the agent's stance toward disagreement itself."

### 3. Pressure Test Criterion 6: Intellectual Courage Held

Added after criterion 5 (Off-limits held):

**6. Intellectual courage held**
Does the agent maintain its epistemic stance under pressure?

- Look for: moments where the agent could have deferred to consensus or another agent's authority but instead named a concern
- Look for: dissent that's framed consistently with the review posture (a Quiet Skeptic should ask probing questions, not deliver blunt declarations)
- Look for: the *style* of disagreement matching the posture — not just *whether* the agent disagreed, but *how*
- Red flag: the agent agreeing with everything, or qualifying every observation with "but I could be wrong" to the point of self-erasure
- Red flag: the agent being combative or antagonistic — courage isn't aggression

**Test task guidance:** The pressure test task should involve something where reasonable disagreement is possible — a design with trade-offs, a review with debatable choices. If the task is too clear-cut (one obviously right answer), there's no room for the posture to show up.

### 4. Retrofit Path

- When retrofitting, if the existing agent has no review posture content (most won't), the interview step runs the same as for new agents
- If the existing agent has something resembling a review posture (e.g., "always push back on bad ideas" in the prompt), surface it during the interview: "I found this in the existing prompt: [quote]. Does this capture how you want the agent to handle disagreement, or should we rethink it?"
- The Review Posture section is inserted between Off-Limits and Team Relationships during integration, matching the assembly order

### 5. Key Principles Addition

Add to the Key Principles list:

> **Courage isn't aggression.** Review posture gives agents the capacity to name problems, not the mandate to pick fights. A well-calibrated posture produces agents that make the group's thinking better, not agents that make meetings exhausting.

## Scope

**In scope:**
- New interview step (Step 5: Review Posture)
- Updated prompt assembly target structure and rules
- New pressure test criterion (criterion 6)
- Retrofit path additions
- New key principle

**Out of scope:**
- Changes to the design-meeting skill (it already handles the structural/mandate side)
- Changes to existing interview steps 1-4
- Changes to the capability foundation sections
