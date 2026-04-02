# Review Posture Dimension Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Add a "Review Posture" personality dimension to the agent-personality skill — a new interview step, prompt assembly section, pressure test criterion, retrofit guidance, and key principle.

**Architecture:** All changes are to a single file: `agent-personality/skills/SKILL.md`. Five additive edits that insert new content and update existing references. No new files, no code, no tests — this is skill prompt content.

**Tech Stack:** Markdown (Claude Code skill format)

**Spec:** `docs/superpowers/specs/2026-04-01-review-posture-dimension-design.md`

---

### Task 1: Add Interview Step 5 — Review Posture

**Files:**
- Modify: `agent-personality/skills/SKILL.md:256-258` (insert between end of Step 4 and Prompt Assembly)

- [ ] **Step 1: Insert the new Step 5 section**

After line 256 (`*Wait for response.*` — end of Step 4: Off-Limits) and before line 258 (`## Prompt Assembly`), insert:

```markdown

### Step 5: Review Posture

"How does [agent name] handle disagreement? When they see a flaw in something everyone else has accepted, what do they do?"

*Wait for response.*

Then explore one dimension at a time:

**Conviction style:** "Does [agent name] lead with their objection, or let it emerge through questions? Do they state 'this is wrong' or ask 'have we considered...?'"

*Wait for response.*

**Persistence:** "When pushed back on, does [agent name] hold firm, soften, or reframe? What would make them drop an objection vs. dig in?"

*Wait for response.*

**Framing:** "How does [agent name] frame dissent — as service to the group, as professional obligation, as intellectual curiosity? What motivates them to speak up?"

*Wait for response.*

Example review postures (use as inspiration, not a menu — push for something specific to this agent):
- "The Loyal Opposition" — frames dissent as strengthening the group's position. Disagrees by showing how the fix makes the whole better.
- "The Quiet Skeptic" — doesn't lead with disagreement, but won't let a flawed assumption pass. Waits, then asks the question nobody asked.
- "The Devil's Advocate" — actively stress-tests ideas by arguing the other side. Not personally invested in the counterposition, but insists it get heard.
- "The Principled Holdout" — stands firm on a position rooted in domain expertise even against unanimous disagreement. Doesn't pick fights, but doesn't fold.

**If the user says "I don't know":** Draft a review posture based on the agent's identity, domain, and principles. An agent whose identity centers on rigor will naturally hold firm on technical points. An agent whose voice is exploratory will naturally dissent through questions. Present the draft: "Based on [agent name]'s identity as [archetype], I'd expect them to handle disagreement like [proposal]. Does that feel right?"

*Wait for response.*

**Quality bar:** A review posture that could apply to any agent is too generic. "Speaks up when they disagree" describes everyone. "Traces the objection back to first principles before naming it, because premature critique kills ideas" — that's specific.
```

- [ ] **Step 2: Update the path sequences to include Step 5**

In the Retrofit Path sequence (around line 50-51 in the original), the sequence currently reads:

```
4. Personality interview (4 steps)
```

Change to:

```
4. Personality interview (5 steps)
```

Similarly for the New Agent path (around line 58-59):

```
3. Personality interview (4 steps)
```

Change to:

```
3. Personality interview (5 steps)
```

- [ ] **Step 3: Verify the section reads naturally after Step 4 and before Prompt Assembly**

Read the file from Step 4 through Prompt Assembly. Confirm the flow: Off-Limits (what the agent refuses) → Review Posture (how the agent handles disagreement) → Prompt Assembly (putting it all together).

- [ ] **Step 4: Commit**

```bash
git add agent-personality/skills/SKILL.md
git commit -s -m "feat: add interview Step 5 — Review Posture

New personality dimension capturing how agents handle intellectual
pressure and disagreement. Includes conviction style, persistence,
framing dimensions, example archetypes as inspiration, and draft-
then-refine path for 'I don't know' responses."
```

---

### Task 2: Update Prompt Assembly — Target Structure and Rules

**Files:**
- Modify: `agent-personality/skills/SKILL.md` (Prompt Assembly section — target structure template and assembly rules)

- [ ] **Step 1: Reorder and update the target structure template**

The current template (lines 264-299 in original) has this ordering at the end: Anti-Patterns → Team Relationships → Off-Limits. The new ordering is: Anti-Patterns → Off-Limits → Review Posture → Team Relationships. In the fenced code block template, replace everything from `## Anti-Patterns` through the closing ` ``` ` with:

```markdown
## Anti-Patterns
[Methodological mistakes to avoid]

## Off-Limits
[Personality-specific boundaries — things this person would never do]

## Review Posture
[How this agent handles disagreement — conviction style, persistence, framing]

## Team Relationships
[Personality-driven descriptions of how this agent relates to teammates]
```

- [ ] **Step 2: Update the assembly rules**

The current rule reads:
```
- **Team Relationships and Off-Limits come last.** They're boundaries — they constrain behavior after capabilities are established.
```

Replace with:
```
- **Off-Limits, Review Posture, and Team Relationships come last.** They form a progression: what the agent refuses to do, how it handles disagreement, and how it relates to specific teammates. Each narrows from general stance to specific dynamics.
```

- [ ] **Step 3: Add the Review Posture assembly rule**

After the updated rule above, add:
```
- **Review Posture bridges Off-Limits and Team Relationships.** It captures the agent's epistemic stance toward disagreement — distinct from what the agent refuses to do (Off-Limits) and how the agent relates to specific teammates (Team Relationships).
```

- [ ] **Step 4: Verify the template and rules are internally consistent**

Read the full Prompt Assembly section. Confirm:
- Template order matches rule descriptions
- No references to the old ordering remain

- [ ] **Step 5: Commit**

```bash
git add agent-personality/skills/SKILL.md
git commit -s -m "feat: update prompt assembly for Review Posture section

Reorder template: Off-Limits before Team Relationships, with new
Review Posture section between them. Update assembly rules to describe
the three-section progression from self-constraint to epistemic stance
to interpersonal dynamics."
```

---

### Task 3: Update Retrofit-Specific Instructions

**Files:**
- Modify: `agent-personality/skills/SKILL.md` (Retrofit-Specific Instructions subsection)

- [ ] **Step 1: Update the Off-Limits retrofit instruction**

The current instruction reads:
```
- **Add Off-Limits at the bottom**, after anti-patterns.
```

Replace with:
```
- **Add Off-Limits, Review Posture, and Team Relationships at the bottom**, after anti-patterns. Off-Limits first, then Review Posture, then Team Relationships — matching the assembly order.
```

- [ ] **Step 2: Add Review Posture retrofit guidance**

After the updated Off-Limits instruction, add:
```
- **Surface existing review-posture-like content.** If the existing prompt has instructions about pushing back, challenging ideas, or handling disagreement (e.g., "always push back on bad ideas"), surface it during the interview: "I found this in the existing prompt: [quote]. Does this capture how you want the agent to handle disagreement, or should we rethink it?" Use it as a starting point rather than discarding it.
```

- [ ] **Step 3: Verify retrofit instructions are consistent with assembly order**

Read the full Retrofit-Specific Instructions. Confirm the ordering guidance matches the template.

- [ ] **Step 4: Commit**

```bash
git add agent-personality/skills/SKILL.md
git commit -s -m "feat: update retrofit path for Review Posture

Add guidance for surfacing existing review-posture-like content in
agent prompts during retrofit. Update Off-Limits placement instruction
to include Review Posture and Team Relationships ordering."
```

---

### Task 4: Add Pressure Test Criterion 6

**Files:**
- Modify: `agent-personality/skills/SKILL.md` (Pressure Test section — evaluate criteria and test design guidance)

- [ ] **Step 1: Update the section heading**

Change:
```
### Evaluate Against 5 Criteria
```

To:
```
### Evaluate Against 6 Criteria
```

- [ ] **Step 2: Add criterion 6 after criterion 5**

After criterion 5 (Off-limits held) and before `### After the Test`, insert:

```markdown

**6. Intellectual courage held**
Does the agent maintain its epistemic stance under pressure?
- Look for: moments where the agent could have deferred to consensus or another agent's authority but instead named a concern
- Look for: dissent that's framed consistently with the review posture (a Quiet Skeptic should ask probing questions, not deliver blunt declarations)
- Look for: the *style* of disagreement matching the posture — not just *whether* the agent disagreed, but *how*
- Red flag: the agent agreeing with everything, or qualifying every observation with "but I could be wrong" to the point of self-erasure
- Red flag: the agent being combative or antagonistic — courage isn't aggression
```

- [ ] **Step 3: Add test task guidance for review posture**

In the "Design the Test" subsection, after the existing guidance about picking a real task, add:

```markdown

For review posture to show up, the task should involve something where reasonable disagreement is possible — a design with trade-offs, a review with debatable choices. If the task is too clear-cut (one obviously right answer), there's no room for the posture to emerge.
```

- [ ] **Step 4: Update the "personality isn't showing up" troubleshooting**

In the "After the Test" subsection, add to the list of common causes:

```
- Review posture is too generic (fix: make the conviction style and framing more specific to this agent's identity)
- The task had no room for disagreement (fix: pick a task with genuine trade-offs or debatable decisions)
```

- [ ] **Step 5: Commit**

```bash
git add agent-personality/skills/SKILL.md
git commit -s -m "feat: add pressure test criterion 6 — intellectual courage

New evaluation criterion for review posture. Includes look-fors for
dissent style consistency, red flags for self-erasure and aggression,
and test task guidance for picking scenarios with room for disagreement."
```

---

### Task 5: Add Key Principle and Final Verification

**Files:**
- Modify: `agent-personality/skills/SKILL.md` (Key Principles section)

- [ ] **Step 1: Add the new principle**

At the end of the Key Principles list (after the "Handle 'I don't know' with proposals" bullet), add:

```markdown
- **Courage isn't aggression.** Review posture gives agents the capacity to name problems, not the mandate to pick fights. A well-calibrated posture produces agents that make the group's thinking better, not agents that make meetings exhausting.
```

- [ ] **Step 2: Read the full file and verify coherence**

Read the complete SKILL.md from top to bottom. Check:
- Step numbering is sequential (1-5)
- Path sequences reference "5 steps" not "4 steps"
- Template order matches assembly rules
- Retrofit instructions are consistent with template
- Pressure test has 6 criteria
- No orphaned references to "4 steps" or "5 criteria" remain

- [ ] **Step 3: Commit**

```bash
git add agent-personality/skills/SKILL.md
git commit -s -m "feat: add 'courage isn't aggression' key principle

Guardrail principle for review posture calibration. Completes the
review posture dimension: interview step, assembly, retrofit,
pressure test, and principle."
```
