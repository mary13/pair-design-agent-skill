# Troubleshooting Flowchart

Decision trees for common Pair Design failure modes. Use these when a session has gone off-track to recover quickly without a full retrospective.

---

## How to use this document

1. Identify the symptom you're seeing.
2. Walk the matching flowchart top-to-bottom.
3. Take the action at the leaf node.
4. Resume the workflow loop.

If multiple symptoms apply, work the highest-severity one first (multi-screen dump > scope creep > momentum > docs).

---

## Symptom 1: Gen produced multiple screens at once

**Severity:** Critical — violates the golden rule.

```
Multiple screens appeared in one response
            │
            ▼
Has Synth reviewed any of them yet?
            │
   ┌────────┴────────┐
   │                 │
  NO                YES (one or more)
   │                 │
   ▼                 ▼
"Stop. Show me     Were they actually
just the first    APPROVED, or just
one. We'll get    skimmed?
to the others."    │
   │          ┌────┴─────┐
   │          │          │
   │       Skimmed   Approved
   │          │          │
   │          ▼          ▼
   │     Treat as    Keep approved
   │     un-reviewed ones, restart
   │          │       review on rest
   │          ▼          │
   └──► Gen re-presents  │
        screen 1 with    │
        rationale,       │
        Synth reviews,   │
        normal loop      │
        resumes  ◄───────┘
```

**Recovery action:** Do not delete the extra artifacts — they may be reusable. But treat anything that wasn't reviewed as a draft, and run each one through the standard review cycle before approving.

**Prevention:** Synth should interrupt as soon as the second artifact appears in a response, before reading further.

---

## Symptom 2: Stuck on a decision

**Severity:** Medium — momentum killer if it persists.

```
Synth can't choose between options
            │
            ▼
How many options on the table?
            │
   ┌────────┼─────────┐
   │        │         │
  1        2-3       4+
   │        │         │
   ▼        ▼         ▼
Why is    Apply     Gen has
there      tie-     given too
even a    breaker:  many.
debate?   "Which is Synth: "Cut
Reframe   easiest   to your top
the       to change 2 — I'll
question. later?"   pick from
   │        │       those."
   ▼        ▼         │
Get one   Pick,       ▼
new       document,  Gen returns
option,   move on.   with 2.
proceed.    │         │
   │        │         ▼
   └────────┴────► Apply tiebreaker
                   above.
```

**Recovery action:** If a decision has been open for more than 5 minutes of session time, force a choice using the "easier to change later" tiebreaker. Document both alternatives in the decision record so the rejected option is preserved for later reconsideration.

**Prevention:** Gen should never present more than 3 options. If there are genuinely more, group them or recommend one.

---

## Symptom 3: Scope is creeping

**Severity:** Medium — quality risk if not caught.

```
New requirement / feature / screen
appearing mid-session
            │
            ▼
Is it required to complete the
CURRENT artifact?
            │
   ┌────────┴────────┐
   │                 │
  YES               NO
   │                 │
   ▼                 ▼
Was this in       Add it to a
the framing?      "parking lot"
   │              file. Continue
┌──┴──┐           current scope.
│     │              │
YES   NO             ▼
│     │           Review parking
▼     ▼           lot at session
Build  STOP.      end — defer,
it.    Reframe:   absorb into
       "This       next scope, or
       changes    drop.
       scope.
       Should we
       expand or
       defer?"
       Synth
       decides.
```

**Recovery action:** Maintain a running parking-lot file (`parking-lot.md` or a section in your session log). Anything that doesn't serve the current artifact goes there immediately — do not stop to design it.

**Prevention:** End each Frame phase with an explicit "in scope / out of scope" list. Reference it when new ideas surface.

---

## Symptom 4: Lost momentum

**Severity:** Medium — sessions that stall rarely recover the same day.

```
Progress has stopped or slowed sharply
            │
            ▼
Why is it stalled?
            │
   ┌────────┼──────────┬──────────┐
   │        │          │          │
Unclear  Decision   Energy    Tooling
problem  paralysis  drained   broken
   │        │          │          │
   ▼        ▼          ▼          ▼
Synth:    See       5-min      Pause
restate   Symptom 2 break.     session.
problem.    │       Review     Fix
Define              quick-     blocker.
"done"              ref.       Restart
for this            Identify   when
artifact.           SMALLEST   ready.
   │                next step.
   ▼                Do JUST
Gen asks:           that.
"What's the
ONE next
step?"
```

**Recovery action:** Shrink the scope of the next step until you can complete it in 5 minutes. Do that, ship it, then re-evaluate. Momentum builds incrementally.

**Prevention:** Set a soft timer (~10 minutes per artifact for typical screens). When you blow past it, audit the cause.

---

## Symptom 5: Documentation is falling behind

**Severity:** Low to medium — easy to recover but loses fidelity if delayed.

```
More than 2 significant decisions
unrecorded
            │
            ▼
PAUSE generation.
            │
            ▼
For each undocumented decision:
    Was it tactical or architectural?
            │
   ┌────────┴────────┐
   │                 │
Tactical          Architectural
   │                 │
   ▼                 ▼
Use the lite     Use the full
template.        template.
~30 sec each.    ~3-5 min each.
   │                 │
   └────────┬────────┘
            ▼
Once caught up, RESUME generation.
Document the next decision while
it's still fresh.
```

**Recovery action:** Stop generating until the backlog is cleared. The fidelity penalty for documenting from memory grows fast — within an hour you've lost the alternatives you considered.

**Prevention:** Document immediately after decision, before starting the next artifact. Treat doc as part of the "approve" step, not as a separate phase.

---

## Symptom 6: Synth and Gen disagree on direction

**Severity:** Medium — productive tension is fine; entrenched conflict is not.

```
Repeated friction on a design choice
            │
            ▼
Is the disagreement about facts,
preferences, or principles?
            │
   ┌────────┼──────────┐
   │        │          │
Facts    Preference  Principle
   │        │          │
   ▼        ▼          ▼
Look it   Synth        Both name
up. User  decides —    the
research, you're       principle.
analytics, the role.   Are they
patterns. Gen          actually in
Whoever   surfaces     conflict?
has data  the trade-     │
wins.     off, then    YES → Synth
   │      moves on.    decides
   │        │          which wins
   │        │          for THIS
   │        │          project,
   │        │          documents
   │        │          rationale.
   │        │          NO → Re-
   │        │          phrase
   │        │          until
   │        │          alignment
   │        │          is clear.
   └────────┴──────────┘
```

**Recovery action:** Name the disagreement type explicitly. Most "stuck" arguments are actually about different categories — once you've named which one it is, the resolution path is usually obvious.

**Prevention:** Gen should explicitly flag when a recommendation is preference-based ("I'd lean toward X but it's a judgment call") vs. principle-based ("X violates progressive disclosure").

---

## Symptom 7: Requirements keep shifting

**Severity:** High — rework risk and demoralization.

```
Synth changed requirements after
gen built something
            │
            ▼
Why did they change?
            │
   ┌────────┼──────────┐
   │        │          │
New info  Synth saw   Original
emerged   the design  framing
(user     and         was wrong
research,  realized
edge       implications
case,
constraint)
   │        │          │
   ▼        ▼          ▼
Acceptable.  Acceptable.  Concerning.
Document     Document     Pause
as DEC.      as DEC.      session.
Adjust       Adjust       Re-do
forward.     forward.     Frame phase
   │            │         from
   │            │         scratch
   │            │         before
   │            │         resuming.
   └────────────┴──────────┘
```

**Recovery action:** Distinguish "iteration on a known target" (good) from "the target itself moved" (worth a Frame redo). The first costs minutes; the second costs hours if not caught.

**Prevention:** End the Frame phase by having synth restate the goal in their own words. If it sounds different from what was originally said, frame again.

---

## Quick-reference card

| Symptom | First move |
|---|---|
| Multiple screens dumped | "Stop. Show me just the first." |
| Decision paralysis | "Easier to change later?" tiebreaker |
| Scope creeping | Parking lot, continue current scope |
| Lost momentum | Shrink next step to 5 minutes |
| Doc backlog | Pause generation, catch up |
| Synth/Gen disagree | Name the type: facts / preference / principle |
| Requirements shifting | Distinguish iteration from re-framing |

---

## When to call a session

Some sessions should end early. Stop and reschedule if:

- More than two red flags have triggered in the last 30 minutes
- Energy is gone for either party
- Requirements have shifted twice in one session (re-frame next time, fresh)
- A blocker exists that can't be resolved in-session (missing research, missing stakeholder input)

Calling a session early is a feature, not a failure. The work that did happen is preserved; the work that would have happened in a fatigued session is usually rework.

---

**Version:** 1.0
**Last Updated:** May 2026
**Pairs with:** `session-checklist.md`, `workflow-diagram.md`
