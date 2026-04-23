# Decision Template

Use this template to document each significant design decision during your Pair Design session.

---

## Decision ID: DEC-XXX

**Date:** YYYY-MM-DD

**Title:** [Short, descriptive title in imperative form]

---

## Context

**Why was this decision needed?**

[Describe the situation that led to this decision. What problem were you solving? What question needed answering? What prompted this choice?]

**Related decisions:** [List any DEC-IDs that connect to this one]

---

## Decision

**What did you decide to do?**

[State the decision clearly and specifically. This should be actionable and concrete.]

---

## Rationale

**Why did you choose this approach?**

[Explain the reasoning behind the decision. What factors were most important? What user needs does this serve? What principles guided this choice?]

---

## Alternatives Considered

**What other options did you explore?**

1. **[Alternative 1]**
   - Description: [Brief explanation]
   - Why not chosen: [Reason for rejection]

2. **[Alternative 2]**
   - Description: [Brief explanation]
   - Why not chosen: [Reason for rejection]

3. **[Alternative 3]** (if applicable)
   - Description: [Brief explanation]
   - Why not chosen: [Reason for rejection]

---

## Consequences

**What are the impacts and trade-offs?**

**Positive consequences:**
- [Benefit 1]
- [Benefit 2]
- [Benefit 3]

**Negative consequences / Trade-offs:**
- [Trade-off 1]
- [Trade-off 2]
- [Trade-off 3]

**Technical implications:**
- [What needs to be built/changed]
- [Dependencies or requirements]
- [Complexity considerations]

---

## Design Patterns

**Which design patterns does this use or establish?**

- [pattern-name-1]
- [pattern-name-2]
- [pattern-name-3]

*Use kebab-case for pattern names (e.g., progressive-disclosure, button-hierarchy)*

---

## User Flows Affected

**Which user flows does this decision impact?**

- [flow-name-1]
- [flow-name-2]

*Use consistent flow naming (e.g., swatch-detour, order-now, password-reset)*

---

## Screens/Files Affected

**Which artifacts were created or modified?**

- [file-name-1.html]
- [file-name-2.html]
- [component-name.tsx]

*Include full file names with extensions*

---

## Tags

**Categorize this decision for future search:**

**Source:**
- [ ] user-request
- [ ] user-feedback
- [ ] design-exploration
- [ ] technical-constraint

**Category:**
- [ ] information-architecture
- [ ] interaction-design
- [ ] visual-design
- [ ] form-design
- [ ] navigation
- [ ] content-design

**Purpose:**
- [ ] conversion-optimization
- [ ] trust-building
- [ ] ux-optimization
- [ ] accessibility
- [ ] performance
- [ ] business-constraint

**Custom tags:** [Add any project-specific tags]

---

## Notes

**Additional context or future considerations:**

[Any extra information that doesn't fit above but might be useful later. Future improvements? Known limitations? Related research?]

---

## Review Checklist

Before finalizing this decision record:

- [ ] Title is clear and descriptive
- [ ] Context explains why decision was needed
- [ ] Decision is stated clearly
- [ ] Rationale explains the "why"
- [ ] At least 2 alternatives are listed
- [ ] Consequences include both positive and negative
- [ ] Design patterns are identified
- [ ] Affected files are listed
- [ ] Tags are selected
- [ ] Decision ID is unique and sequential

---

## Example (for reference)

### Decision ID: DEC-009

**Date:** 2026-04-22

**Title:** Split payment from shipping screen

**Context:**
Initially designed shipping and payment collection on a single screen. User provided feedback that this felt overwhelming and mixed two distinct mental tasks.

**Decision:**
Create separate screen for payment methods instead of combining with shipping information.

**Rationale:**
Better focus on each task, reduced cognitive load, clearer action hierarchy. Shipping and payment are conceptually distinct - shipping is about "where" and payment is about "how." Separating them respects this mental model.

**Alternatives Considered:**

1. **Combined form with all fields on one screen**
   - Why not: Too much information at once, higher abandonment risk

2. **Accordion sections on one screen**
   - Why not: Still requires page scanning, doesn't truly separate tasks

3. **Tabbed interface**
   - Why not: Adds UI complexity, tab pattern not appropriate for linear flow

**Consequences:**

*Positive:*
- Improved expected completion rate
- Clearer error handling
- Better mobile experience
- Each screen has single purpose

*Negative/Trade-offs:*
- Added one screen to flow (may feel longer to some users)
- Requires additional routing logic
- One more back/forward transition

*Technical:*
- Created path-1-step-3-payment.html
- Modified navigation links
- Added payment-specific validation

**Design Patterns:**
- progressive-disclosure
- single-purpose-screen
- chunking

**User Flows Affected:**
- swatch-detour

**Screens Affected:**
- path-1-step-3.html
- path-1-step-3-payment.html

**Tags:**
- user-request
- information-architecture
- payment
- form-design

---

**Template Version:** 1.0
**Last Updated:** April 2026
**Compatible with:** decisions.json format
