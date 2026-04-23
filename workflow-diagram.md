# Pair Design Workflow Diagrams

Visual representations of the Pair Design methodology for collaborative design work.

---

## 🔄 The Core Workflow Loop

```
┌─────────────────────────────────────────────────────────────────┐
│                    PAIR DESIGN WORKFLOW                         │
└─────────────────────────────────────────────────────────────────┘

    ┌──────────────┐
    │   1. FRAME   │  ◄── Synth defines the problem
    └──────┬───────┘
           │
           ▼
    ┌──────────────┐
    │ 2. GENERATE  │  ◄── Gen creates ONE artifact
    └──────┬───────┘
           │
           ▼
    ┌──────────────┐
    │  3. REVIEW   │  ◄── Synth gives feedback
    └──────┬───────┘
           │
           ▼
    ┌──────────────┐      Need changes?
    │  4. ITERATE  │  ────────┐
    └──────┬───────┘          │
           │ Approved          │
           ▼                   │
    ┌──────────────┐          │
    │ 5. DOCUMENT  │          │
    └──────┬───────┘          │
           │                   │
           ▼                   │
    ┌──────────────┐          │
    │   6. NEXT    │          │
    └──────┬───────┘          │
           │                   │
           │  More work?       │
           └───────────────────┘
                   │
                   ▼ Done
              ┌─────────┐
              │ COMPLETE│
              └─────────┘
```

---

## 👥 Role Interactions

```
┌────────────────────────────────────────────────────────────────┐
│              SYNTH (Human) ←→ GEN (AI)                         │
└────────────────────────────────────────────────────────────────┘

SYNTH                                    GEN
(Human)                                  (AI)
   │                                      │
   │  1. Frame problem                    │
   ├─────────────────────────────────────>│
   │     "Design login screen"            │
   │                                      │
   │  2. Clarify requirements             │
   │<─────────────────────────────────────┤
   │     "Email or social login?"         │
   │                                      │
   │  3. Provide direction                │
   ├─────────────────────────────────────>│
   │     "Both options"                   │
   │                                      │
   │  4. Present ONE artifact             │
   │<─────────────────────────────────────┤
   │     [Shows login wireframe]          │
   │     + Rationale                      │
   │                                      │
   │  5. Give specific feedback           │
   ├─────────────────────────────────────>│
   │     "Social buttons too small"       │
   │                                      │
   │  6. Show revision                    │
   │<─────────────────────────────────────┤
   │     [Updated wireframe]              │
   │                                      │
   │  7. Approve                          │
   ├─────────────────────────────────────>│
   │     "Good, next screen"              │
   │                                      │
   │  8. Ask about next                   │
   │<─────────────────────────────────────┤
   │     "Password reset or signup?"      │
   │                                      │
   └──────────────────┬───────────────────┘
                      │
                   REPEAT
```

---

## ⚠️ The Golden Rule in Action

```
┌────────────────────────────────────────────────────────────────┐
│         NEVER DUMP MULTIPLE SCREENS AT ONCE                    │
└────────────────────────────────────────────────────────────────┘

❌ WRONG WAY:                    ✅ RIGHT WAY:

Gen: "Here are 5 screens:"      Gen: "Here's screen 1:"
    [Screen 1]                      [Screen 1]
    [Screen 2]                      + Rationale
    [Screen 3]
    [Screen 4]                  Synth: "Good, next"
    [Screen 5]
                                Gen: "Here's screen 2:"
Synth: Overwhelmed!                 [Screen 2]
       Can't review all             + Rationale
       Quality suffers
                                Synth: "Change button color"

                                Gen: "Here's revised screen 2:"
                                    [Screen 2 updated]

                                Synth: "Perfect, next"

                                ... continues one at a time
```

---

## 🎯 Decision Points Flow

```
┌────────────────────────────────────────────────────────────────┐
│                    DECISION FLOW                               │
└────────────────────────────────────────────────────────────────┘

                    Start Work
                        │
                        ▼
              ┌─────────────────┐
              │ Clear what to   │
              │ create?         │
              └────┬───────┬────┘
                   │       │
              YES  │       │  NO
                   │       │
                   │       └────> ASK: Clarify requirements
                   │                     │
                   │              ◄──────┘
                   ▼
              ┌─────────────────┐
              │ Create ONE      │
              │ artifact        │
              └────┬────────────┘
                   │
                   ▼
              ┌─────────────────┐
              │ Multiple viable │
              │ approaches?     │
              └────┬───────┬────┘
                   │       │
              YES  │       │  NO
                   │       │
                   │       └────> Create single solution
                   │                     │
                   ▼                     │
         ┌─────────────────┐            │
         │ Present 2-3     │            │
         │ options with    │            │
         │ trade-offs      │            │
         └────┬────────────┘            │
              │                         │
              │  ◄──────────────────────┘
              ▼
         ┌─────────────────┐
         │ Synth reviews   │
         └────┬────────────┘
              │
              ▼
         ┌─────────────────┐
         │ Approved?       │
         └────┬───────┬────┘
              │       │
         YES  │       │  NO
              │       │
              │       └────> Iterate: Apply feedback
              │                     │
              │              ◄──────┘
              ▼
         ┌─────────────────┐
         │ Significant     │
         │ decision?       │
         └────┬───────┬────┘
              │       │
         YES  │       │  NO
              │       │
              ▼       └────────┐
         ┌─────────────────┐   │
         │ Document        │   │
         │ decision        │   │
         └────┬────────────┘   │
              │                │
              │  ◄─────────────┘
              ▼
         ┌─────────────────┐
         │ More work?      │
         └────┬───────┬────┘
              │       │
         YES  │       │  NO
              │       │
              └───────┤       └────> Done!
                      │
                      ▼
              Back to "Create ONE artifact"
```

---

## 🚨 Red Flag Detection System

```
┌────────────────────────────────────────────────────────────────┐
│                   RED FLAG MONITORING                          │
└────────────────────────────────────────────────────────────────┘

During Session: Continuous Monitoring
        │
        ├──> Multiple screens created?  ──> ⛔ STOP
        │         │                           │
        │         NO                          └──> Show only first one
        │                                          Review one at a time
        │
        ├──> Major decision without discussion? ──> ⛔ STOP
        │         │                                  │
        │         NO                                 └──> Present options
        │                                                 Get approval
        │
        ├──> Work proceeding without feedback? ──> ⛔ STOP
        │         │                                  │
        │         NO                                 └──> Request review
        │                                                 Wait for direction
        │
        ├──> Requirements assumed? ──> ⛔ STOP
        │         │                      │
        │         NO                     └──> Ask clarifying questions
        │                                     Confirm understanding
        │
        └──> Scope creeping? ──> ⛔ STOP
                  │                 │
                  NO                └──> Note for later
                                        Refocus on current scope

        All Clear: Continue Working
```

---

## 📋 Complete Session Flow

```
┌────────────────────────────────────────────────────────────────┐
│               COMPLETE PAIR DESIGN SESSION                     │
└────────────────────────────────────────────────────────────────┘

PRE-SESSION
│
├─ Define roles (Synth/Gen)
├─ Frame problem clearly
├─ Share context & constraints
├─ Set success criteria
└─ Identify first artifact
    │
    ▼
SESSION START
│
└─ Open quick-reference.md
   Open session-checklist.md
   Have decision-template.md ready
    │
    ▼
MAIN LOOP ─────────────────────┐
│                              │
├─ Gen: Ask clarifying Qs      │
├─ Gen: Create ONE artifact    │
├─ Gen: Explain rationale      │
│   │                          │
│   ▼                          │
├─ Synth: Review artifact      │
├─ Synth: Give specific feedback│
├─ Synth: Make decision        │
│   │                          │
│   ├─ Needs changes? ─> Iterate
│   │                          │
│   ├─ Approved? ────────┐     │
│   │                    │     │
│   ▼                    ▼     │
├─ Document decision    Note   │
│  (if significant)   patterns │
│   │                    │     │
│   ▼                    ▼     │
├─ Identify next artifact      │
│                              │
└─ More work? ─────────────────┘
    │
    NO
    ▼
SESSION END
│
├─ Review all artifacts
├─ Complete documentation
├─ Identify patterns
├─ Organize files
├─ Plan next session
└─ Run retrospective
    │
    ▼
COMMIT & SHARE
```

---

## 🎨 Artifact Creation Detail

```
┌────────────────────────────────────────────────────────────────┐
│            CREATING A SINGLE ARTIFACT                          │
└────────────────────────────────────────────────────────────────┘

1. UNDERSTAND
   │
   ├─ What is the artifact?
   ├─ What problem does it solve?
   ├─ Who will use it?
   ├─ What's the context?
   └─ Any constraints?
       │
       ▼

2. EXPLORE OPTIONS
   │
   ├─ Option A: [Approach]
   │   └─ Pros/Cons
   ├─ Option B: [Approach]
   │   └─ Pros/Cons
   └─ Option C: [Approach]
       └─ Pros/Cons
       │
       ▼

3. CHOOSE DIRECTION (Synth decides)
   │
   └─ Selected: Option B
       │
       ▼

4. CREATE
   │
   ├─ Build the artifact
   ├─ Apply established patterns
   ├─ Ensure consistency
   └─ Keep it focused
       │
       ▼

5. PRESENT
   │
   ├─ Show the artifact
   ├─ Explain rationale
   ├─ Note design patterns used
   ├─ Mention trade-offs
   └─ Request feedback
       │
       ▼

6. REVIEW & ITERATE
   │
   ├─ Synth reviews
   ├─ Identifies issues
   ├─ Suggests changes
   │   │
   │   ├─ Critical? ──> Fix immediately
   │   ├─ Important? ──> Fix now
   │   └─ Nice to have? ──> Note for later
   │
   └─ Revise and re-present
       │
       ▼

7. APPROVE
   │
   └─ Artifact ready for next step
```

---

## 🔀 When Things Go Wrong

```
┌────────────────────────────────────────────────────────────────┐
│                 RECOVERY PROCEDURES                            │
└────────────────────────────────────────────────────────────────┘

PROBLEM: Multiple screens created
│
├─ STOP immediately
├─ Acknowledge: "One at a time please"
├─ Gen: Show only first screen
├─ Synth: Review thoroughly
├─ Complete full review cycle
└─ Then proceed to next
    │
    ▼ RECOVERED


PROBLEM: Can't decide between options
│
├─ Use tiebreaker: "Which is easier to change later?"
├─ OR: Document both as alternatives
├─ Choose one to implement now
├─ Note the other for potential future
└─ Move forward
    │
    ▼ RECOVERED


PROBLEM: Scope creeping
│
├─ STOP adding features
├─ Create "parking lot" document
├─ Add new ideas there
├─ Review current scope
├─ Refocus on original goals
└─ Continue with scope
    │
    ▼ RECOVERED


PROBLEM: Losing momentum
│
├─ Take 5-minute break
├─ Review quick-reference.md
├─ Check session goals
├─ Identify smallest next step
├─ Do just that one thing
└─ Build momentum incrementally
    │
    ▼ RECOVERED


PROBLEM: Documentation falling behind
│
├─ PAUSE artifact creation
├─ Catch up on documentation
├─ Document recent decisions
├─ Update decision database
├─ Then resume creation
└─ Keep doc current going forward
    │
    ▼ RECOVERED
```

---

## 📊 Success Metrics Flow

```
┌────────────────────────────────────────────────────────────────┐
│              MEASURING SUCCESS                                 │
└────────────────────────────────────────────────────────────────┘

PROCESS QUALITY
│
├─ One artifact per iteration? ────> ✓ or ✗
├─ All artifacts reviewed? ────────> ✓ or ✗
├─ Decisions made promptly? ────────> ✓ or ✗
├─ Documentation complete? ─────────> ✓ or ✗
└─ Agreements followed? ────────────> ✓ or ✗
    │
    All ✓ ? ──> HIGH QUALITY PROCESS
    │
    ▼

OUTPUT QUALITY
│
├─ Serves intended purpose? ────────> ✓ or ✗
├─ User needs addressed? ───────────> ✓ or ✗
├─ Patterns consistent? ────────────> ✓ or ✗
├─ Rationale documented? ───────────> ✓ or ✗
└─ Trade-offs understood? ──────────> ✓ or ✗
    │
    All ✓ ? ──> HIGH QUALITY OUTPUT
    │
    ▼

COLLABORATION QUALITY
│
├─ Roles respected? ────────────────> ✓ or ✗
├─ Feedback actionable? ────────────> ✓ or ✗
├─ Both parties engaged? ───────────> ✓ or ✗
├─ Feels collaborative? ────────────> ✓ or ✗
└─ Steady progress? ────────────────> ✓ or ✗
    │
    All ✓ ? ──> HIGH QUALITY COLLABORATION
    │
    ▼

OVERALL SUCCESS = All three areas showing ✓
```

---

## 🎯 Quick Reference: The Essential Pattern

```
┌────────────────────────────────────────────────────────────────┐
│                    THE ESSENTIAL PATTERN                       │
└────────────────────────────────────────────────────────────────┘

        ONE ARTIFACT AT A TIME

                    │
                    ▼
            ┌───────────────┐
            │    CREATE     │
            └───────┬───────┘
                    │
                    ▼
            ┌───────────────┐
            │    REVIEW     │
            └───────┬───────┘
                    │
                    ▼
            ┌───────────────┐
            │   APPROVE     │
            └───────┬───────┘
                    │
                    ▼
            ┌───────────────┐
            │   DOCUMENT    │
            └───────┬───────┘
                    │
                    ▼
            ┌───────────────┐
            │     NEXT      │
            └───────────────┘

        NEVER SKIP STEPS
        NEVER COMBINE STEPS
        NEVER RUSH THROUGH
```

---

**Version:** 1.0
**Last Updated:** April 2026
**Print this:** Keep visible during sessions
**Share this:** With team members learning the methodology
