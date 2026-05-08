# Lightweight Decision Template

For tactical, easy-to-change, single-screen decisions where the heavy template is overkill.

**Use this when:** the decision is reversible, affects one screen or component, and someone could undo it in 10 minutes if needed. Otherwise use `decision-template.md`.

**Time to fill:** ~30 seconds.

---

## Format

```
DEC-XXX | YYYY-MM-DD | [Short title]

What:        [One sentence — what we chose]
Why:         [One sentence — the main reason]
Considered:  [One alternative we rejected, and why]
Trade-off:   [The cost of this choice]
Affects:     [file or component]
```

---

## Example

```
DEC-014 | 2026-04-22 | Use "Continue" not "Next" on flow buttons

What:        All forward-progress buttons say "Continue", not "Next" or "Submit".
Why:         Conveys forward motion without implying a final commit.
Considered:  "Next" — too neutral, doesn't signal intent. Rejected.
Trade-off:   Slightly longer label; minor space cost in narrow layouts.
Affects:     all flow screens
```

---

## When to upgrade to the full template

Promote a lite decision to the full `decision-template.md` if any of these become true:

- More than one alternative is worth recording
- The decision affects multiple flows or components
- There's a real trade-off that future you will want to understand
- You catch yourself wanting to write more than two sentences in any field
- The decision turns out to be harder to reverse than you thought

When upgrading, copy the existing fields into the full template and fill the missing sections.

---

## Anti-patterns

- **Using lite for architectural decisions** — if it touches information architecture, flow structure, or affects more than 2 files, use the full template.
- **Skipping "Considered"** — even one rejected alternative shows that thinking happened. If you truly considered nothing else, the decision probably wasn't worth recording.
- **Vague "Why"** — "it's better" is not a reason. Name the user need, principle, or constraint that drove it.

---

## Storage

Lite decisions can live inline in a session log, in a single `decisions-lite.md` running list, or as entries in `decisions.json` with a `"weight": "lite"` field. The format is the same regardless of where it lives.

---

**Template version:** 1.0
**Pairs with:** `decision-template.md` (heavy)
