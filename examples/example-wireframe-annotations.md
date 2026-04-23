# Example: Wireframe Annotations

**How to document wireframes with design rationale**

This example shows how to annotate a wireframe with the reasoning behind design decisions. Based on the swatch selection screen from the Tailor Onboarding project.

---

## Screen: Swatch Selection

**File:** `path-1-step-2.html`
**Flow:** Swatch detour path
**Step:** 2 of 10
**User task:** Select up to 5 fabric swatches to receive

---

## 📐 Wireframe (ASCII Representation)

```
┌───────────────────────────────────────────────────────────┐
│ Select up to 5 swatches                            (1)    │
│ We'll send them overnight                          (2)    │
│                                                            │
│ ┌─────────────────────┐  ┌──────────────────────────────┐│
│ │                     │  │ Silk charmeuse          (3)  ││
│ │                     │  │ ☐ Navy   ☐ Blush            ││
│ │    Dress Preview    │  │ ☐ Emerald ☐ Black           ││
│ │    ┌───────────┐    │  │                              ││
│ │    │ Updates   │(4) │  │ Silk crepe              (3)  ││
│ │    │ as you    │    │  │ ☐ Ivory  ☐ Burgundy         ││
│ │    │ select    │    │  │ ☐ Slate  ☐ Champagne        ││
│ │    └───────────┘    │  │                              ││
│ │                     │  │ Cotton sateen           (3)  ││
│ │    sticky (5)       │  │ ☐ White  ☐ Coral            ││
│ │                     │  │ ☐ Sage   ☐ Navy stripe      ││
│ │                     │  │                              ││
│ └─────────────────────┘  │ Linen blend             (3)  ││
│                          │ ☐ Natural ☐ Terracotta       ││
│                          │ ☐ Denim   ☐ Charcoal         ││
│                          │                              ││
│                          │ Wool crepe              (3)  ││
│                          │ ☐ Camel   ☐ Forest           ││
│                          │ ☐ Plum    ☐ Gray             ││
│                          └──────────────────────────────┘│
│                                                            │
│ 0/5 selected                                        (6)    │
│                                                            │
│ [Continue]                                          (7)    │
│ Cancel                                              (8)    │
└───────────────────────────────────────────────────────────┘
```

---

## 🔍 Annotations

### (1) Clear Task Statement
```
"Select up to 5 swatches"
```

**Why this works:**
- States the task clearly and concisely
- Includes the constraint (5 maximum) upfront
- Sets expectations before user starts selecting

**Rationale:**
- Users need to know the limit before making choices
- "Up to 5" is more flexible than "Select 5" (allows fewer)
- Direct, action-oriented language

**Alternatives considered:**
- "Choose swatches" - too vague, no limit stated
- "Pick your favorite 5 fabrics" - assumes user will pick 5
- "Swatch selection (max 5)" - more formal, less friendly

**Pattern:** `constrained-choice`, `clear-task-statement`

---

### (2) Delivery Expectation
```
"We'll send them overnight"
```

**Why this works:**
- Reduces friction by stating speed
- Manages expectations upfront
- Makes swatch option more appealing

**Rationale:**
- "Overnight" addresses common concern: "How long will this take?"
- Positioned right after task statement for visibility
- Brevity keeps focus on selection task

**Alternatives considered:**
- No statement - rejected, delivery time is key concern
- "Fast shipping available" - vague, not specific
- Full pricing here - rejected, too much information, pricing comes later

**Pattern:** `expectation-setting`, `friction-reduction`

---

### (3) Fabric Type Grouping
```
Silk charmeuse
Silk crepe
Cotton sateen
Linen blend
Wool crepe
```

**Why this works:**
- Groups by fabric type (not color)
- 5 types = 5 categories
- Scannable hierarchy

**Rationale:**
- Fabric type is primary differentiator (drape, weight, texture)
- Color is secondary (within each fabric type)
- Users can explore one type fully before moving to next
- Corresponds to physical swatch categories

**Alternatives considered:**
- Group by color families - rejected, doesn't match fabric properties
- Flat list of all options - rejected, 20 options overwhelming
- Dropdown selector - rejected, hides options from view

**Pattern:** `progressive-disclosure`, `hierarchical-information`

**Decision reference:** DEC-001 (Add swatch delivery option)

---

### (4) Dynamic Dress Preview
```
┌───────────┐
│ Updates   │
│ as you    │
│ select    │
└───────────┘
```

**Why this works:**
- Shows dress in selected fabrics
- Provides immediate visual feedback
- Helps users imagine final product

**Rationale:**
- Reduces uncertainty about how fabric looks on dress style
- Visual preview more powerful than text descriptions
- Real-time updates create engaging, responsive feel
- Helps users compare fabrics visually

**Alternatives considered:**
- Static dress image - rejected, doesn't show selected fabrics
- No preview - rejected, text alone insufficient for fabric decision
- Separate preview page - rejected, breaks flow and comparison ability

**Pattern:** `show-don't-tell`, `immediate-feedback`, `visual-decision-support`

**Technical implementation:**
- JavaScript updates preview on checkbox change
- Pre-loaded fabric texture images
- Smooth transitions between fabrics

---

### (5) Sticky Positioning
```
sticky
```

**Why this works:**
- Preview stays visible while scrolling
- Users can scroll fabric list while seeing preview
- Enables comparison without losing context

**Rationale:**
- Fabric list is long (5 groups × 4 options = 20 items)
- Users need to scroll to see all options
- Preview should remain visible for comparison
- Sticky positioning solves this elegantly

**Alternatives considered:**
- Fixed positioning - rejected, covers content on mobile
- Scroll both - rejected, users lose preview reference
- Shorter list with pagination - rejected, harder to compare across pages

**Pattern:** `persistent-context`, `comparison-support`

**Technical implementation:**
- CSS: `position: sticky; top: 8px;`
- Works on desktop and tablet
- Gracefully degrades on older browsers

---

### (6) Real-time Counter
```
0/5 selected
```

**Why this works:**
- Shows progress toward limit
- Updates immediately on selection
- Clear visual feedback

**Rationale:**
- Users need to know how many they've selected
- "X/5" format shows both current and maximum
- Prevents accidental over-selection
- Encourages thoughtful curation (limited resource)

**Alternatives considered:**
- No counter - rejected, users don't know their progress
- "You can select 5 more" - rejected, requires mental math
- Only show when near limit - rejected, important information should be visible

**Pattern:** `real-time-feedback`, `progress-indicator`, `constraint-visibility`

**Technical implementation:**
- JavaScript event listener on checkboxes
- Updates on every change
- Disables unchecked boxes when 5 reached

**Decision reference:** DEC-006 (Limit swatch selection to 5)

---

### (7) Primary Action
```
[Continue]
```

**Why this works:**
- Clear next step
- Primary button styling (dark background)
- Positioned where users expect it

**Rationale:**
- Progressive flow requires explicit "next step" action
- Button (vs link) signals importance
- Single-word "Continue" is clear and concise
- Users can proceed even with 0 selections (flexibility)

**Alternatives considered:**
- "Next" - rejected, "Continue" better conveys forward progress
- "Add to cart" - rejected, not making purchase yet
- Auto-advance at 5 - rejected, removes user control
- Disabled until selections made - rejected, too restrictive

**Pattern:** `progressive-disclosure`, `clear-next-action`

---

### (8) Secondary Action
```
Cancel
```

**Why this works:**
- Provides escape path
- Text-only (vs button) shows secondary importance
- Returns to swatch decision screen

**Rationale:**
- Users should always have way to go back
- "Cancel" is clearer than "Back" (this is a selection screen, not form)
- Lower visual priority than Continue (text link vs button)
- Doesn't lose user's place (can restart if needed)

**Alternatives considered:**
- No cancel option - rejected, users need escape path
- "Back" - less clear what happens to selections
- Same styling as Continue - rejected, visual hierarchy unclear
- Browser back button only - rejected, should be explicit option

**Pattern:** `escape-path`, `secondary-action`

---

## 🎨 Design Patterns Applied

### Layout Pattern: Two-Column Preview + Form
- **Left:** Dress preview (visual reference)
- **Right:** Selection interface (interaction)
- **Benefit:** See result while making choices
- **Reused:** Yes, in other fabric selection screens

### Input Pattern: Checkboxes with Limit
- **Why:** Multiple selection (vs radio single choice)
- **Limit enforcement:** JavaScript disables at 5
- **Visual feedback:** Counter shows progress
- **Reused:** Pattern established, not reused elsewhere in this project

### Feedback Pattern: Real-time Updates
- **Preview:** Updates on checkbox change
- **Counter:** Updates on checkbox change
- **Disabling:** Happens immediately at limit
- **Reused:** Yes, pattern applied to other interactive screens

---

## 📊 User Flow Context

**Previous screen:** Swatch decision (yes/no to swatches)
**This screen:** Select which swatches
**Next screen:** Shipping information for swatches

**User mindset:**
- Excited about seeing fabrics
- Uncertain about which ones to choose
- Wants to make good choices
- Conscious of the 5-limit constraint

**Success criteria for this screen:**
- User can easily scan all fabric options
- User can visualize fabrics on dress
- User understands the 5-limit
- User can proceed confidently with selections

---

## 💡 Lessons Learned

### What Worked Well
1. **Visual preview:** Users loved seeing dress update in real-time
2. **5-limit constraint:** Helped focus decision rather than overwhelming
3. **Fabric grouping:** Clear structure made scanning easy
4. **Counter:** Immediate feedback prevented confusion

### What Could Improve
1. **Fabric descriptions:** Could add brief texture/drape descriptions
2. **Comparison feature:** "Compare selected" button to see all choices together
3. **Save selection:** Ability to save and come back later
4. **Recommendations:** "Popular combinations" or "Customers also selected"

### Iteration Notes
- Initial version had no counter - added after recognizing need
- Preview was added later - dramatically improved engagement
- Sticky positioning added when testing revealed scrolling issue

---

## 🔗 Related Decisions

- **DEC-001:** Add swatch delivery option (created this screen)
- **DEC-006:** Limit swatch selection to 5 (counter + disabling)
- **DEC-013:** Placeholder dress image (preview pattern)
- **DEC-015:** Radio vs checkboxes (checkboxes for multiple selection)

---

## 📝 Documentation Tips

### When annotating your own wireframes:

**Do:**
- ✓ Explain WHY, not just WHAT
- ✓ Include alternatives you considered
- ✓ Note patterns being applied or established
- ✓ Reference related decisions
- ✓ Document technical implementation approach
- ✓ Include user mindset and context

**Don't:**
- ✗ Just describe what's visible (wireframe shows that)
- ✗ Skip the rationale (most important part)
- ✗ Ignore alternatives (shows no deliberation)
- ✗ Forget patterns (they should be reusable)
- ✗ Write only for yourself today (write for team in 6 months)

### Annotation Format Options

**Numbered callouts** (like this example):
- Clear reference points
- Works well for complex screens
- Easy to add/remove annotations

**Inline comments:**
- Good for simple screens
- Less visual clutter
- Harder to add extensive rationale

**Separate sections:**
- "Layout", "Interactions", "Content", "Patterns"
- Works for very complex screens
- Can be more organized but harder to follow

---

## 🎯 Using This Example

**When documenting your own screens:**
1. Start with wireframe (even rough sketch)
2. Number key elements
3. Annotate each numbered element
4. Include: Why, Rationale, Alternatives, Pattern
5. Add context (previous/next, user mindset)
6. Note related decisions
7. Document lessons learned

**When reviewing documentation:**
- Check if WHY is explained
- Verify alternatives were considered
- Ensure patterns are identified
- Confirm context is clear
- Look for lessons learned

---

**Screen documented:** April 22, 2026
**Documentation created:** April 23, 2026
**Project:** Tailor Onboarding Flow
**Pattern library:** Growing (reuse these patterns)
