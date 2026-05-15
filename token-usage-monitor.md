# Token Usage Monitor

Token-conscious Pair Design — how to think about context costs during a session, what a healthy session looks like, and what unhealthy patterns reveal about methodology drift.

This is a guidance doc, not a script. The "monitor" is your attention. Most AI assistants surface running token counts somewhere; the value of this file is interpreting what those numbers mean for the design work.

---

## Why this matters

The one-artifact-at-a-time rule is usually framed as a quality control. It's also a token control:

- Each AI response reprocesses the full session as input.
- Long, dense responses inflate every subsequent turn.
- A session that dumps five screens at once doesn't just hurt review — it permanently weights the context with unreviewed work that the model keeps re-reading.

Token discipline and design discipline point in the same direction.

---

## Four things to watch

This document covers each in order. Use them together — any single metric in isolation is misleading.

| Signal | What it tells you |
|---|---|
| **Session totals** | Whether you're approaching context limits and need to summarize |
| **Per-artifact breakdown** | Whether individual responses are bloated |
| **Synth vs Gen split** | Whether the role balance is healthy |
| **Cost estimate** | Whether the session is economically sustainable |

---

## 1. Session totals

### Rules of thumb

- **1 token ≈ 4 characters ≈ 0.75 words** in English.
- A fully filled heavy decision record: ~500–700 tokens.
- A lite decision record: ~80–120 tokens.
- An ASCII wireframe with annotations: ~300–800 tokens.
- A typical Gen turn (artifact + rationale + question): ~800–2000 output tokens, plus the full session as input.

### Budget bands

For a session designing one user flow (5–10 screens), expect:

| Band | Total tokens | What it means |
|---|---|---|
| **Healthy** | < 30k | Tight, disciplined session. Likely under 10 iterations per artifact. |
| **Normal** | 30k–80k | Typical for a productive multi-screen flow with documentation. |
| **Heavy** | 80k–150k | Either complex work or some inefficiency. Audit per-artifact sizes. |
| **At risk** | 150k+ | Approaching context-window pressure on most models. Summarize and continue, or split into a fresh session. |

These numbers scale with context window size. The point isn't the absolute number — it's that you should know roughly where you are.

### When to summarize

If you're crossing into the "Heavy" band:

1. Pause generation
2. Write a session-summary block: 5–10 bullets covering decisions made, patterns established, current artifact in progress
3. Reference the summary in subsequent turns instead of re-quoting earlier work
4. Drop full transcripts of approved artifacts; keep their decision records

Summarization is a methodology checkpoint, not just a token trick — it's a natural moment to verify you're still on-scope.

---

## 2. Per-artifact breakdown

Track tokens output per Gen turn. The shape of the distribution matters more than the average.

### Healthy distribution

```
turn 1 (framing reply):    ~150 tokens
turn 2 (clarifying Q):     ~100 tokens
turn 3 (artifact 1):     ~1,200 tokens
turn 4 (revision):         ~400 tokens
turn 5 (artifact 2):     ~1,400 tokens
turn 6 (clarifying Q):     ~120 tokens
turn 7 (artifact 3):     ~1,100 tokens
```

Notice: clarifying questions are cheap, artifacts cluster around 1,000–1,500 tokens, revisions are smaller than originals.

### Warning shapes

**The bloated artifact**
```
turn 5 (artifact 2):     ~4,800 tokens
```
A single Gen turn above ~3,000 tokens almost always contains multiple artifacts smuggled together, or excessive rationale. Check if the response is actually one artifact.

**The runaway preamble**
```
turn 7 (artifact 3):     ~2,100 tokens (rationale: 1,400, artifact: 700)
```
Rationale should be roughly equal to or smaller than the artifact itself. If rationale dominates, Gen is over-explaining instead of asking.

**The exploding revision**
```
turn 4 (revision):       ~2,800 tokens
```
Revisions larger than originals usually mean Gen rebuilt instead of edited. Ask for a diff-style response.

### Quick rule

If a Gen turn is over 3,000 output tokens, ask "is this one artifact or several?" before approving it.

---

## 3. Synth vs Gen split

Healthy Pair Design has asymmetric turn lengths. Synth turns are short framings, decisions, and feedback. Gen turns include the artifact plus reasoning. A 5–15x output ratio (Gen-to-Synth) is normal.

### Reading the split

| Pattern | Likely cause | Methodology read |
|---|---|---|
| Synth turns < 50 tokens consistently | Synth is just saying "yes, next" | Approval is too cheap — review may be shallow |
| Synth turns growing turn-over-turn | Synth losing trust, over-explaining | Gen isn't asking enough clarifying questions; Synth compensating |
| Synth turns > Gen turns in output | Wrong role balance | Synth is doing Gen's job — consider role swap explicitly |
| Gen turns clustering at exactly the same size | Template padding | Gen is hitting rationale length on autopilot rather than fitting the artifact |

### What "healthy" sounds like

```
Synth: "Add a delivery dropdown with three tiers: overnight $20,
       2-3 day $15, 5-day $8."                              [~50 tokens]

Gen:   "Got it. Should the dropdown go on this screen or
       a new shipping screen?"                              [~25 tokens]

Synth: "New screen — collect email and address there too."  [~25 tokens]

Gen:   [creates the new shipping screen + rationale]      [~1,200 tokens]
```

Short, decisive Synth turns; one focused Gen turn per artifact. Asymmetric, not lopsided.

---

## 4. Cost estimate

Pricing changes; treat these as illustrative orders of magnitude.

### Representative pricing (per million tokens)

| Model class | Input | Output |
|---|---|---|
| Small (Haiku-class) | ~$1 | ~$5 |
| Mid (Sonnet-class) | ~$3 | ~$15 |
| Large (Opus-class) | ~$15 | ~$75 |

### Translating to per-artifact cost

A single artifact iteration on a mid-tier model with a 30k-token session context:

```
Input cost:   30k × $3/MTok    = $0.09
Output cost:  1.5k × $15/MTok  = $0.0225
─────────────────────────────────────────
Per artifact: ~$0.11
```

A 10-screen flow at this rate: ~$1.10. Cheap.

The same flow on a large model with a 100k-token bloated context:

```
Input cost:   100k × $15/MTok  = $1.50
Output cost:  2k × $75/MTok    = $0.15
─────────────────────────────────────────
Per artifact: ~$1.65
```

10 screens: ~$16.50. Same design output, ~15x cost. The difference isn't model choice — it's session hygiene.

### When cost should trigger action

- **>$0.50 per artifact on mid-tier:** session context has bloated; summarize or trim
- **>$2.00 per artifact:** stop and audit — almost certainly a methodology problem
- **Cost per decision documented < $0.05:** you're under-documenting, not saving money

---

## Red flags from token signals

These map to specific methodology problems:

| Token signal | Methodology diagnosis | First move |
|---|---|---|
| Total session > context-window budget | Lost scope discipline, too much in one session | Summarize, then continue or split |
| Single Gen turn > 3,000 tokens | Multi-screen dump (Symptom 1 in troubleshooting) | "One at a time — show me just the first" |
| Synth turn > 500 tokens consistently | Over-framing or losing trust in Gen | Reframe more crisply; check that Gen is asking clarifying questions |
| Cost per decision > $0.50 | Decisions are too heavy or context too bloated | Switch to `decision-template-lite.md` where appropriate |
| Output growing turn over turn | Gen is including more rationale to compensate for something | Ask what's missing from the framing |
| No clarifying questions for 5+ turns | Gen is assuming requirements | Synth should ask, "What did you assume to build this?" |

---

## Practical token-saving moves

In rough order of leverage:

1. **Use the lite decision template** for tactical choices. Saves ~400–600 tokens per decision recorded.
2. **Reference patterns by name** rather than re-describing them. After establishing `two-column-preview-layout`, say "use the established two-column-preview-layout" not "use a layout with the preview on the left and the form on the right…"
3. **Keep wireframes ASCII** until late-stage detail is needed. ASCII boxes are ~1/3 the tokens of equivalent prose descriptions.
4. **Summarize at natural breakpoints** — between flows, after major decisions. Don't wait until you hit a limit.
5. **Drop approved-artifact full text** once captured in a decision record. The record IS the artifact's representation in context.
6. **Ask clarifying questions early.** A 50-token question prevents a 3,000-token wrong artifact.
7. **Resist the urge to re-explain rationale** once a pattern is established. The first time a decision is made, document the reasoning fully. The second time it's applied, just name the pattern.

---

## A simple in-session monitor

You don't need tooling. At the start of each session, jot down:

```
SESSION: [name]
DATE: [date]
MODEL: [model class]
BUDGET: [token target] / [cost target]

LOG:
turn N — [synth/gen] — [~tokens] — [what happened]
turn N+1 — ...

CHECKPOINTS:
- [ ] At ~30k tokens: audit per-artifact sizes
- [ ] At ~60k tokens: consider summarization
- [ ] At ~90k tokens: summarize or split session
```

A running tally on a sticky note is enough. The exercise of writing it down is what changes behavior.

---

## When to ignore this document

- **Truly tiny sessions** (single decision, single screen): the overhead of tracking exceeds any savings.
- **Exploratory phases:** when you're deliberately ranging wide to find the right framing, tight token budgets fight that work. Set the budget after the framing is stable.
- **Final polish passes:** small revisions are cheap; obsessing over them is false economy.

The point of the monitor is to catch methodology drift early, not to optimize every turn.

---

**Version:** 1.0
**Last Updated:** May 2026
**Pairs with:** `troubleshooting-flowchart.md`, `session-checklist.md`
