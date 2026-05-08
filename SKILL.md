---
name: pair-design
description: "Use this skill for collaborative UX/UI design work — designing user flows, creating wireframes or prototypes, working through interaction design problems, or making structured design decisions where iteration and rationale matter. Triggers include: 'design a flow', 'create a wireframe', 'let's pair design', 'I need to design X', 'walk me through designing Y', requests for prototype screens, mentions of UX/UI methodology, interaction design, information architecture, or service design. The skill enforces a disciplined one-artifact-at-a-time methodology with clear human-AI roles (Synth/Gen) and decision documentation. Do NOT use for: simple bug fixes, pure implementation tasks without design decisions, quick one-off visual changes, or document/spreadsheet/presentation creation (use docx/xlsx/pptx skills instead)."
license: MIT
---

# Pair Design

A collaborative design methodology adapted from Noessel & Anderson's *Pair Design* for human-AI work.

## The golden rule

**Never produce multiple screens or artifacts in one response.** Work one step at a time: create → review → iterate → approve → document → next.

This is the foundation. Everything else flows from it.

## Roles

### Gen (the AI)

- Propose options and alternatives
- Generate **one** artifact per response, with rationale
- Ask clarifying questions before building when requirements are ambiguous
- Surface major decisions as choices for synth, don't decide unilaterally
- Wait for feedback before producing the next artifact

### Synth (the human)

- Frame the problem, share context, define success criteria
- Give specific, actionable feedback ("button hierarchy unclear" — not "looks off")
- Make decisions when gen presents options
- Catch agreement violations early and call them out

Roles can swap when the human wants to propose a specific solution or the AI needs to clarify requirements.

## Workflow

1. **Frame** — Synth defines the problem, context, constraints, success criteria
2. **Generate** — Gen creates ONE artifact with rationale and any alternatives considered
3. **Review** — Synth gives specific feedback
4. **Iterate** — Refine based on feedback until approved
5. **Document** — Capture significant decisions (see template selection below)
6. **Next** — Move to the next artifact

Loop steps 2–6 until the objective is met.

## Red flags — stop immediately if any occur

- Multiple screens dumped without approval
- Major architectural decision made without discussion
- Work proceeding without feedback
- Requirements assumed instead of confirmed
- Scope expanding beyond the agreed focus

When a red flag triggers: pause, name the violation, return to the agreement, continue.

## Working in autonomous / async mode

When the human is away between turns (Cowork-style long sessions):

- Still produce only ONE artifact per response
- Batch open questions clearly at the end so the human can answer them in one pass
- Use reasonable defaults for low-stakes tactical choices and flag them explicitly: "I assumed X — say so if you want it different"
- Never decide architectural questions autonomously; surface them as choices and stop

## Choosing a decision template

Not every choice needs a heavy ADR. Match the template to the stakes:

| Decision type | Template | Examples |
|---|---|---|
| Architectural, strategic, hard to reverse | `decision-template.md` | Information architecture, flow structure, payment vs. shipping split |
| Tactical, easy to change, single-screen | `decision-template-lite.md` | Button label, copy, color, icon choice |
| Trivial | None — mention in passing | Spacing tweaks, ordering of two items |

If you find yourself debating which to use, default to the lite template.

## Files in this skill

**Methodology**

- `SKILL.md` — This file: agent entry point and core rules
- `pair-design-skill.md` — Long-form methodology reference
- `README.md` — Quick start guide for humans
- `quick-reference.md` — One-page cheat sheet
- `workflow-diagram.md` — ASCII workflow visuals
- `session-checklist.md` — Pre/during/post session checks
- `troubleshooting-flowchart.md` — Recovery procedures when sessions go off-track

**Templates**

- `decision-template.md` — Heavy template for architectural decisions
- `decision-template-lite.md` — Quick template for tactical decisions

**Examples**

- `examples/example-session.md` — Annotated session transcript
- `examples/example-decisions.json` — Sample decision database
- `examples/example-wireframe-annotations.md` — Annotated wireframe documentation

## Common phrases

**Starting a session:** "Let's pair design this. I'll be synth, you be gen. Here's what I need to design…"

**Gen asking for direction:** "Before I build this, should I…?" / "Two options — which direction?"

**Catching a violation:** "Hold on — one screen at a time please. Show me just the first one."

**Closing an iteration:** "Good, next." / "Move on." / "Let's do the next screen."

## Reference

Based on *Pair Design* by Chris Noessel & Molly Anderson, adapted for human-AI collaboration. Proven on the Tailor Onboarding project: 16 screens, 15 documented decisions, zero scope creep.
