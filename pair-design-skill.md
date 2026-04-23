# Pair Design Skill

A collaborative design methodology based on Noessel & Anderson's Pair Design approach, adapted for human-AI collaboration.

## Overview

This skill enables structured collaborative design work between a human (synth) and AI (gen), with clearly defined roles, agreements, and workflows.

## When to Use This Skill

Use this skill when:
- Starting a new UX/UI design project
- Designing user flows and interactions
- Creating prototypes or wireframes
- Making design decisions that require iteration
- Working through complex design problems collaboratively

**Do NOT use for:**
- Pure implementation tasks without design decisions
- Bug fixes or maintenance work
- Quick one-off changes

## Roles

### Gen (Generator) - AI Role
**Responsibilities:**
- Propose options and alternatives
- Explore possibilities
- Generate wireframes, flows, and prototypes
- Present design choices with rationale
- Build artifacts one step at a time

**Constraints:**
- Never dump multiple screens or artifacts at once
- Always present options rather than single solutions
- Ask before making major decisions
- Show work incrementally
- Document decisions as they're made

### Synth (Synthesizer) - Human Role
**Responsibilities:**
- Frame the problem and context
- Evaluate presented options
- Make final decisions on direction
- Provide feedback at each step
- Keep project on track

**Constraints:**
- Give clear, actionable feedback
- Make decisions when options are presented
- Don't let gen proceed without direction
- Frame requirements before asking for generation

### Role Flexibility
Roles can swap when:
- Human wants to propose a specific solution
- AI needs to clarify requirements before generating
- Context requires different expertise distribution

## Core Agreements

### Gen Agreements

1. **Work one step at a time**
   - Build single screens, flows, or components
   - Wait for feedback before proceeding
   - Never create multiple artifacts in one response

2. **Show work as we go**
   - Present work immediately when created
   - Explain rationale for each decision
   - Make thinking visible

3. **Never dump multiple screens**
   - This is the most critical agreement
   - One screen/artifact per iteration
   - Prevents overwhelm and ensures thoughtful review

4. **Ask before major decisions**
   - Present options for significant choices
   - Don't assume requirements
   - Clarify ambiguity before building

5. **Swap roles when needed**
   - Recognize when synth should generate
   - Ask for role swap if appropriate
   - Adapt to project needs

### Synth Agreements

1. **Frame the problem clearly**
   - Provide context and constraints upfront
   - Define success criteria
   - Share relevant background

2. **Give feedback on each step**
   - Review each artifact as presented
   - Provide specific, actionable feedback
   - Don't let work accumulate without review

3. **Make decisions when options presented**
   - Choose direction when gen presents alternatives
   - Don't defer decision-making indefinitely
   - Be decisive to maintain momentum

4. **Keep us on track**
   - Redirect if work veers off course
   - Maintain focus on current goal
   - Call out when agreements are broken

### Shared Agreements

1. **Progressive disclosure**
   - Reveal complexity gradually
   - Start simple, add sophistication
   - Build from core to edge cases

2. **User-centered design**
   - Keep user needs central
   - Reference personas, scenarios, jobs-to-be-done
   - Design for real use cases

3. **Iterate based on feedback**
   - Expect to refine and revise
   - No artifact is final on first pass
   - Improvement comes through iteration

4. **Document as we build**
   - Capture decisions and rationale
   - Record alternatives considered
   - Build institutional knowledge

## Red Flags (Stop and Ask First)

These situations require explicit discussion before proceeding:

1. **Multiple screen dumps**
   - Gen creates more than one screen/artifact without approval
   - Action: Stop, review one at a time, get feedback

2. **Major architectural changes**
   - Fundamental shifts in approach or structure
   - Action: Present options with trade-offs, get explicit approval

3. **Skipping user feedback**
   - Moving forward without synth review
   - Action: Pause, present work, wait for direction

4. **Assumptions about requirements**
   - Building based on guessed needs
   - Action: Ask clarifying questions first

5. **Scope creep**
   - Adding features or complexity beyond current focus
   - Action: Note for later, stay focused on current step

## Workflow

### Phase 1: Frame
**Synth leads**

1. Define the design problem
2. Share context (users, constraints, goals)
3. Establish success criteria
4. Identify first artifact to create

**Gen responds:**
- Clarify any ambiguity
- Confirm understanding
- Propose approach

### Phase 2: Generate
**Gen leads**

1. Create single artifact (wireframe, flow, component)
2. Explain design rationale
3. Present alternatives if applicable
4. Ask for feedback

**Synth responds:**
- Review the artifact
- Provide specific feedback
- Make decision on direction
- Approve next step or request revision

### Phase 3: Iterate
**Collaborative**

1. Refine based on feedback
2. Build next step incrementally
3. Maintain documentation
4. Repeat until objective met

### Phase 4: Document
**Gen leads**

1. Capture final decisions
2. Record rationale and alternatives
3. Note patterns established
4. Create reusable components

**Synth responds:**
- Review documentation
- Add context gen might have missed
- Approve for future reference

## Best Practices

### For Gen (AI)

- **Start with questions** - Clarify before creating
- **Present options** - Rarely is there only one solution
- **Explain rationale** - Why this design choice?
- **Reference patterns** - Build on established conventions
- **Stay focused** - One artifact at a time
- **Show alternatives** - What didn't you choose and why?

### For Synth (Human)

- **Be specific** - "I don't like this" → "The button hierarchy is unclear"
- **Provide context** - Share the "why" behind decisions
- **Make decisions** - Don't let options pile up
- **Trust the process** - Slow is smooth, smooth is fast
- **Document as you go** - Future you will thank you
- **Catch violations** - Call out when agreements are broken

## Common Patterns

### Decision Documentation Pattern
After each significant decision, document:
- **Context:** Why was this needed?
- **Decision:** What did we choose?
- **Rationale:** Why this over alternatives?
- **Alternatives:** What else did we consider?
- **Consequences:** What are the trade-offs?

### Option Presentation Pattern
When presenting alternatives:
1. Show 2-4 options (not 1, not 10)
2. Explain each approach
3. Note trade-offs
4. Recommend one (if appropriate)
5. Let synth decide

### Feedback Incorporation Pattern
When receiving feedback:
1. Confirm understanding
2. Ask clarifying questions if needed
3. Show revised version
4. Explain what changed and why
5. Check if it addresses feedback

## Anti-Patterns to Avoid

### For Gen
- ❌ Creating full page sets without approval
- ❌ Making major decisions without presenting options
- ❌ Moving to next step without feedback
- ❌ Assuming requirements not explicitly stated
- ❌ Building complexity before establishing basics

### For Synth
- ❌ Vague feedback ("make it better")
- ❌ Changing requirements mid-iteration
- ❌ Skipping review of presented work
- ❌ Requesting multiple screens at once
- ❌ Not documenting decisions

## Output Artifacts

This skill produces:

**Design Artifacts:**
- Wireframes (one at a time)
- User flows (step by step)
- Prototypes (incremental)
- Component designs (reusable)

**Documentation:**
- Design decisions database
- Rationale for choices
- Alternatives considered
- Pattern library
- Session logs

## Success Metrics

You're using this skill well when:
- ✓ Each iteration produces exactly one artifact
- ✓ Every artifact gets reviewed before proceeding
- ✓ Decisions are documented with rationale
- ✓ Patterns emerge and get reused
- ✓ Both roles feel collaborative, not directive
- ✓ Work flows steadily without overwhelm
- ✓ Quality improves through iteration

## Example Session

```
Synth: "I need to design a checkout flow for a custom dress shop.
       Users need to provide measurements, choose fabric, and pay."

Gen:   "Before I start, a few questions:
       - What's the biggest user anxiety in this flow?
       - Do we have existing patterns to follow?
       - Should we tackle measurements, fabric, or payment first?"

Synth: "Biggest anxiety is getting measurements right.
       No existing patterns - this is new.
       Let's start with the fabric choice screen."

Gen:   "I'll create a fabric selection screen.
       Should this show all options at once, or
       filter by type (silk, cotton, etc) first?"

Synth: "Show all at once - we only have about 20 fabrics total."

Gen:   [Creates single fabric selection screen wireframe]
       "Here's the fabric selection screen. I used:
       - Radio buttons (single choice)
       - Fabric preview images
       - Short descriptions
       - Dress preview that updates

       Alternative would be a dropdown, but visual selection
       seems better for fabric choice. Thoughts?"

Synth: "I like this. Can you add the dress preview as a sticky
       element so it stays visible while scrolling?"

Gen:   [Shows revised version with sticky preview]
       "Updated with sticky preview. Good to move to next screen?"

Synth: "Yes, let's do measurements next."

Gen:   [Creates measurements screen]
       ...
```

## Integration with Other Tools

This skill works well with:
- **Decision databases** - Capture choices systematically
- **Design systems** - Build reusable patterns
- **Prototyping tools** - Create interactive artifacts
- **User research** - Ground decisions in user needs
- **Session logs** - Document process over time

## Troubleshooting

### "We're moving too slowly"
- Check: Are you doing one screen at a time? (Good!)
- Check: Is feedback specific and actionable?
- Check: Are decisions being made promptly?
- Remember: Slow is smooth, smooth is fast

### "Work feels directionless"
- Synth: Frame the problem more clearly
- Define success criteria upfront
- Break down into smaller steps
- Check: Are we answering the right question?

### "Too many options, can't decide"
- Gen: Present fewer options (2-3 max)
- Gen: Make a recommendation
- Synth: Use "which is easiest to change later?" as tiebreaker
- Document the decision and move forward

### "We keep revisiting decisions"
- Document decisions immediately
- Include rationale and alternatives
- Mark decisions as "tentative" or "final"
- Time-box exploration phases

## Adapting This Skill

This skill can be adapted for:
- **Solo design work** - Switch between roles yourself
- **Team collaboration** - Multiple humans, one gen
- **Different domains** - Architecture, content design, etc.
- **Client work** - Client as synth, designer as gen
- **Teaching** - Student as synth, learning design process

## Version History

- **v1.0** (April 2026) - Initial version based on Tailor Onboarding project
- Derived from Noessel & Anderson's Pair Design methodology
- Adapted for human-AI collaboration

## Credits

- Based on: Pair Design by Chris Noessel & Molly Anderson
- Developed during: Tailor Onboarding Flow project
- Tested on: Scenario A (Event-Driven First-Timer)
- Results: 16 screens, 15 documented decisions, zero scope creep

---

**To use this skill:** Invoke at the start of a design session. Reference agreements throughout. Document violations as learning opportunities.
