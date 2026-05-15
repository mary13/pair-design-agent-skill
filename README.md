# Pair Design Agent Skill

This folder contains an agent skill for collaborative design work using the Pair Design methodology.

## What is This?

The **Pair Design Skill** is a structured methodology for human-AI collaborative design work, based on Noessel & Anderson's Pair Design principles, adapted from our successful Tailor Onboarding project.

## Quick Start

### For New Design Projects

1. **Before you start**
   - Open `quick-reference.md` - Keep visible during session
   - Open `session-checklist.md` - Use pre-session setup
   - Have `decision-template.md` ready for documenting choices

2. **Start your design session**
   ```
   "Let's use the Pair Design methodology from the skill file"
   ```

3. **Frame the problem (Synth role)**
   - Define what you're designing
   - Share context and constraints
   - Establish success criteria
   - Check session-checklist.md "Pre-Session Setup"

4. **Generate incrementally (Gen role)**
   - AI creates one artifact at a time
   - Reviews and rationale provided
   - Options presented when appropriate
   - Reference quick-reference.md for common phrases

5. **Iterate collaboratively**
   - Review each artifact
   - Provide feedback
   - Make decisions
   - Document choices using decision-template.md
   - Monitor session-checklist.md "During Session" checks

6. **Wrap up**
   - Complete session-checklist.md "Wrap-Up" section
   - Ensure all decisions documented
   - Plan next session

## Files in This Folder

**Core Documentation:**
- `SKILL.md` - Agent entry point with frontmatter (auto-loadable) ✓
- `pair-design-skill.md` - Complete long-form methodology documentation
- `README.md` - This file (quick start guide for humans)
- `workflow-diagram.md` - Visual workflow representations ✓

**Essential Tools:**
- `quick-reference.md` - One-page cheat sheet ✓
- `decision-template.md` - Heavy template for architectural decisions ✓
- `decision-template-lite.md` - Lightweight template for tactical decisions ✓
- `session-checklist.md` - Pre/during/post session checklists ✓
- `troubleshooting-flowchart.md` - Recovery procedures for common failure modes ✓
- `token-usage-monitor.md` - Token-conscious session guidance and budget bands ✓

**Metadata & Configuration:**
- `skill.json` - Skill metadata and formal packaging ✓

**Examples:**
- `examples/example-session.md` - Annotated session transcript ✓
- `examples/example-decisions.json` - Sample decision database ✓
- `examples/example-wireframe-annotations.md` - Design documentation ✓

## Core Principles

### The Most Important Rule
**Never dump multiple screens/artifacts at once**

This is the foundation of Pair Design. Work one step at a time.

### The Three Agreements

**Gen (AI) Agreements:**
- Work one step at a time
- Show work as we go
- Ask before major decisions

**Synth (Human) Agreements:**
- Frame the problem clearly
- Give feedback on each step
- Make decisions when options presented

**Shared Agreements:**
- Progressive disclosure
- User-centered design
- Document as we build

## When to Use This Skill

✅ **Use for:**
- Designing user flows
- Creating wireframes/prototypes
- Making design decisions
- UX/UI design projects
- Complex interaction design

❌ **Don't use for:**
- Simple bug fixes
- Pure implementation tasks
- Quick one-off changes

## Typical Session Flow

```
1. Frame      → You define the problem
2. Generate   → AI creates one artifact
3. Review     → You provide feedback
4. Iterate    → Refine and improve
5. Document   → Capture decisions
6. Next       → Move to next artifact
```

Repeat steps 2-6 until project complete.

## Success Indicators

You're doing it right when:
- ✓ Each iteration produces exactly one artifact
- ✓ Every artifact gets reviewed before moving on
- ✓ Decisions are documented with rationale
- ✓ Work feels collaborative, not rushed
- ✓ Both roles are engaged

## Red Flags

Stop and recalibrate if:
- ⚠️ Multiple screens appear at once
- ⚠️ Major decisions made without discussion
- ⚠️ Work proceeds without feedback
- ⚠️ Requirements are assumed, not confirmed

## Example Exchange

```
You (Synth):
"I need to design a password reset flow. Users should
be able to reset via email or SMS."

AI (Gen):
"Before I start, should I begin with the entry point
(forgot password link) or the method selection screen?"

You (Synth):
"Start with the method selection - assume they've
already clicked 'forgot password'."

AI (Gen):
[Creates single method selection screen]
"Here's the method selection screen with two options:
email and SMS. I included:
- Clear description of each method
- Security indicators
- Expected delivery time

Should this be radio buttons or two distinct buttons?"

You (Synth):
"Two distinct buttons - makes it feel like a choice
rather than a form. Looks good!"

AI (Gen):
"Great. Next screen - should I do the email flow
or SMS flow first?"
```

## Results from Original Project

This methodology successfully produced:
- **16 prototype screens** (one at a time)
- **15 documented decisions** (with rationale)
- **2 complete user flows** (10 + 6 screens)
- **Zero scope creep**
- **High design quality** through iteration

## Adapting for Your Project

The skill works for:
- Web design
- Mobile app design
- Service design
- Content design
- Information architecture
- Interaction design

Adjust the artifacts (wireframes, flows, content, etc.) to your domain.

## Decision Documentation

This skill naturally produces decision documentation.

**Use the decision-template.md** for each significant decision:
- Copy the template for each decision
- Fill in all sections (context, rationale, alternatives, consequences)
- Assign sequential Decision IDs (DEC-001, DEC-002, etc.)
- Tag appropriately for future querying

**Optional: Create a decisions.json** for queryable records:
- Structured JSON format
- Enables programmatic queries
- See `examples/example-decisions.json` for format and query examples

## Common Questions

**Q: What if I want multiple screens?**
A: Ask for them one at a time. Each screen gets full attention and review.

**Q: What if the AI generates multiple screens anyway?**
A: Point out the violation: "Let's follow Pair Design - one screen at a time please. Show me just the first one."

**Q: Can I use this for solo work?**
A: Yes! Switch between roles yourself. Frame as synth, generate as gen.

**Q: How long should each iteration take?**
A: Varies by complexity. Simple screen: 5-10 minutes. Complex flow: 20-30 minutes. The key is completing the review before moving on.

**Q: What if we need to go back and change something?**
A: That's expected! Iteration is built in. Just be clear about what needs changing and why.

## Tips for Success

### For Humans (Synth)

1. **Be specific in feedback**
   - Not: "I don't like this"
   - Instead: "The call-to-action isn't prominent enough"

2. **Make timely decisions**
   - Don't let options pile up
   - Use "easy to change later" as tiebreaker
   - Document and move forward

3. **Catch violations early**
   - If AI dumps multiple screens, stop immediately
   - Remind of the agreements
   - Review one screen at a time

### For AI (Gen)

1. **Ask before assuming**
   - Clarify ambiguous requirements
   - Present options for decisions
   - Don't guess what synth wants

2. **Show your thinking**
   - Explain design rationale
   - Share alternatives considered
   - Note trade-offs

3. **Stay focused**
   - One artifact per response
   - Wait for feedback
   - Document as you go

## Resources

- **Source methodology:** Pair Design by Noessel & Anderson
- **Reference implementation:** Tailor Onboarding Flow project (proven on 16 screens, 15 decisions, zero scope creep)
- **Sample decision database:** `examples/example-decisions.json`
- **Sample session transcript:** `examples/example-session.md`

## Contributing Improvements

As you use this skill, consider:
- Adding example sessions
- Creating quick reference guides
- Documenting adaptations for specific domains
- Sharing lessons learned

## Version

**Current version:** 1.0 (April 2026)

Based on successful application in Tailor Onboarding project (Scenario A).

---

**Ready to start?** `SKILL.md` is the agent-loadable entry point with the core rules. `pair-design-skill.md` has the complete long-form methodology. Or just jump in with:

*"Let's use Pair Design methodology - I'll be synth, you be gen. Here's what I need to design..."*
