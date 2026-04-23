# Example Pair Design Session

**Project:** Tailor Onboarding Flow - Scenario A
**Session:** Designing the swatch selection screen
**Duration:** ~25 minutes
**Participants:** Kathleen (Synth) + Claude (Gen)

---

## 📋 Pre-Session Setup

**Synth framed the problem:**
- Design onboarding for custom dress shop
- User needs to choose fabric
- Option to order swatches first vs order directly
- Progressive disclosure principle

**Success criteria:**
- Clear fabric selection interface
- Support both swatch and direct order paths
- Maintain dress preview
- Limit to 5 swatches for cost management

---

## 💬 Session Transcript with Annotations

### Exchange 1: Clarification Before Building

```
Synth: "There is one flow with a swatch detour. She requests
       swatches overnight, gets them, returns to order the dress."

Gen:   "She will want to choose fabric colors and patterns along
       with fabric types. How should we present this—grouped by
       fabric type with color options under each?"
```

**🔍 ANNOTATION:**
- ✅ Gen asks clarifying question BEFORE creating
- ✅ Presents option for structure instead of assuming
- ✅ Shows understanding of the requirement
- **Pattern:** Always clarify ambiguous requirements first

---

### Exchange 2: Making Design Decisions

```
Synth: "Yes, fabric selection. Text label is enough for now."

Gen:   "Should the swatch selection show all fabric types with
       checkboxes (up to 5 total), or filter by type first?"
```

**🔍 ANNOTATION:**
- ✅ Synth makes clear decision ("text label")
- ✅ Gen asks about next design decision (selection method)
- ✅ Presents two distinct approaches
- **Pattern:** Get decisions on one aspect before building

---

### Exchange 3: User Provides Direction

```
Synth: "Show all fabric types with checkboxes up to 5 total."
```

**🔍 ANNOTATION:**
- ✅ Clear, specific direction
- ✅ Confirms the approach
- ✅ Includes constraint (5 limit)
- **Pattern:** Synth provides decisive direction

---

### Exchange 4: Single Screen Creation

```
Gen:   [Creates ONLY the swatch selection screen]

       "I've created the swatch selection screen with:
       - Two-column layout (dress preview + fabric selection)
       - 5 fabric types: silk charmeuse, silk crepe, cotton
         sateen, linen blend, wool crepe
       - 4 color/pattern options per fabric type
       - Checkboxes for multiple selection
       - Counter showing 0/5 selected
       - JavaScript to enforce 5-limit

       The layout keeps the dress preview visible as they select,
       and the counter updates in real-time. Should this have a
       'Continue' button or auto-advance when 5 are selected?"
```

**🔍 ANNOTATION:**
- ✅ **CRITICAL:** Only ONE screen created (not multiple)
- ✅ Shows the artifact immediately
- ✅ Explains design rationale
- ✅ Lists what was included
- ✅ Asks for feedback on remaining decision
- **Pattern:** Single artifact + rationale + question

---

### Exchange 5: Specific Feedback

```
Synth: "Continue button. We should have a dropdown where she can
       have overnight $20, 2-3 days $15, 5 days $8"
```

**🔍 ANNOTATION:**
- ✅ Answers the question (Continue button)
- ✅ Adds new requirement (delivery speed dropdown)
- ⚠️  New requirement = new screen needed
- **Pattern:** Feedback may reveal additional requirements

---

### Exchange 6: Scope Management

```
Gen:   "Got it. Should I add the delivery dropdown to this screen,
       or create a separate shipping information screen?"
```

**🔍 ANNOTATION:**
- ✅ Catches potential scope creep
- ✅ Asks about information architecture
- ✅ Presents two options
- ⚠️  Could have continued to next screen, but clarified first
- **Pattern:** When requirements expand, ask about structure

---

### Exchange 7: Information Architecture Decision

```
Synth: "Create a separate screen. Collect email and shipping
       address there, along with the delivery speed dropdown."
```

**🔍 ANNOTATION:**
- ✅ Makes architectural decision
- ✅ Defines what goes on the new screen
- ✅ Keeps current screen focused
- **Pattern:** Separate concerns into different screens

---

### Exchange 8: Moving to Next Artifact

```
Gen:   "Before I create the shipping screen, should payment be on
       that screen too, or separate?"
```

**🔍 ANNOTATION:**
- ✅ Pauses before creating next artifact
- ✅ Asks about next structural decision
- ✅ Thinks ahead to avoid rework
- **Pattern:** Ask architectural questions upfront

---

### Exchange 9: Another Architecture Decision

```
Synth: "I think we should have a separate screen for payment methods."
```

**🔍 ANNOTATION:**
- ✅ Clear decision
- ✅ Separates shipping from payment
- 📝 This became DEC-009 in decision database
- **Pattern:** User feedback shapes information architecture

---

### Exchange 10: Creating Second Screen

```
Gen:   [Creates ONLY the shipping information screen]

       "Here's the shipping information screen with:
       - Email field (labeled 'For order updates')
       - Full name
       - Street address
       - Apt/Suite (optional)
       - City, State, ZIP
       - Delivery speed dropdown with pricing
       - 'Continue to payment' button
       - Back button

       This separates shipping from payment for better focus.
       Good to proceed to payment screen?"
```

**🔍 ANNOTATION:**
- ✅ Only ONE screen (the shipping screen, not payment)
- ✅ Lists all elements
- ✅ Explains rationale (separation)
- ✅ Asks permission before next screen
- **Pattern:** Complete one screen before moving to next

---

### Exchange 11: Approval and Progress

```
Synth: "Yes, build the payment screen."
```

**🔍 ANNOTATION:**
- ✅ Clear approval
- ✅ Direction to proceed
- ✅ Current screen implicitly approved
- **Pattern:** Approval before moving forward

---

## 📊 Session Outcomes

**Artifacts Created:** 3 screens (one at a time)
1. Swatch selection screen
2. Shipping information screen
3. Payment screen (created after this exchange)

**Decisions Documented:**
- DEC-009: Split payment from shipping screen
- Fabric selection method (checkboxes, 5-limit)
- Delivery pricing tiers
- Information architecture (3 separate screens)

**Patterns Established:**
- Two-column layout (preview + form)
- Delivery speed dropdown pattern
- Separation of concerns (shipping vs payment)

**Time Breakdown:**
- Screen 1: ~8 minutes (questions + creation + review)
- Screen 2: ~7 minutes (questions + creation + review)
- Screen 3: ~6 minutes (faster, pattern established)
- Documentation: ~4 minutes (captured during work)

---

## ✅ What Made This Session Successful

### Agreement Compliance
- ✓ One screen at a time (never dumped multiple)
- ✓ Clarifying questions before building
- ✓ Rationale provided with each artifact
- ✓ Feedback requested explicitly
- ✓ Decisions made promptly

### Gen (AI) Behaviors
- ✓ Asked before assuming
- ✓ Presented options for decisions
- ✓ Explained design rationale
- ✓ Waited for approval before proceeding
- ✓ Caught potential scope issues

### Synth (Human) Behaviors
- ✓ Provided clear direction
- ✓ Made timely decisions
- ✓ Gave specific feedback
- ✓ Shaped information architecture
- ✓ Kept session focused

### Collaboration Quality
- ✓ Both roles engaged
- ✓ Feedback loop healthy
- ✓ Steady progress
- ✓ No confusion or rework
- ✓ Productive tension between exploration and decision

---

## 🚩 Red Flags Avoided

### Did NOT Happen:
- ❌ Multiple screens created at once
- ❌ Work proceeded without feedback
- ❌ Major decisions made without discussion
- ❌ Requirements assumed
- ❌ Scope crept unchecked

### How We Avoided Them:
- One screen at a time enforced strictly
- Explicit approval requested before each new screen
- Architectural questions asked upfront
- New requirements surfaced and discussed
- Scope expansion managed (separate screen vs same screen)

---

## 💡 Key Takeaways

### For Gen (AI):
1. **Ask before building** - Get clarity on approach first
2. **One at a time** - Even when you can see the next 5 screens
3. **Explain rationale** - Help synth understand your choices
4. **Present options** - Rarely is there only one way
5. **Wait for approval** - Don't assume approval is implicit

### For Synth (Human):
1. **Be decisive** - Don't defer decisions indefinitely
2. **Be specific** - "I don't like it" → "Button hierarchy unclear"
3. **Make trade-offs** - Perfect is the enemy of good
4. **Trust the process** - One screen feels slow but prevents rework
5. **Document as you go** - Decisions are fresh now

### For Both:
1. **Slow is smooth, smooth is fast** - Disciplined pace beats rushing
2. **Catch violations immediately** - Gently redirect to agreements
3. **Document significant decisions** - Your future self will thank you
4. **Iterate fearlessly** - Everything can be refined
5. **Celebrate progress** - Each completed screen is an achievement

---

## 📝 Documentation Generated

After this session, the following were documented:

**Decision Records:**
- DEC-009: Split payment from shipping screen
  - Context, rationale, alternatives, consequences
  - Tagged: user-request, information-architecture, form-design
  - Screens affected: path-1-step-3.html, path-1-step-3-payment.html

**Session Notes:**
- Patterns established (two-column layout, delivery dropdown)
- Information architecture decisions
- Next steps identified

**Artifacts:**
- 3 HTML files committed to repository
- Decision database updated
- Patterns noted for reuse

---

## 🎯 Using This Example

**When learning Pair Design:**
1. Read through the transcript
2. Notice the annotations highlighting methodology
3. See how agreements prevent problems
4. Observe the rhythm: ask → create → review → approve → next

**When running your own sessions:**
1. Reference this for pacing
2. Use similar phrases ("Should I...?", "Before I create...")
3. Notice when to pause and ask
4. Follow the pattern of one artifact at a time

**When teaching others:**
1. Show this as concrete example
2. Point out the annotations
3. Discuss what made it successful
4. Contrast with what could have gone wrong

---

**Session Date:** April 22, 2026
**Project Repository:** https://github.com/mary13/tailor-onboarding
**Methodology:** Pair Design (Noessel & Anderson)
**Outcome:** 3 high-quality screens, 0 rework, clear architecture
