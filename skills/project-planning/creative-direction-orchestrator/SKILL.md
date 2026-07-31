---
name: creative-direction-orchestrator
description: Orchestrates a structured design council using concept, art direction, editorial, brand, conversion, motion, and creative-technology specialist skills. Use when the user asks to solve an open-ended design problem, redesign a page or website, compare competing creative directions, reconcile visual ambition with conversion and feasibility, or produce one unified creative strategy and implementation plan.
license: MIT
compatibility: Portable Agent Skill. Works best when its related specialist skills are installed or accessible through a skill registry or repository file access.
metadata:
  category: project-planning
  task_type: planner
  audience: designers-frontend-developers-creative-directors-product-teams
  tags:
    - design-strategy
    - creative-direction
    - orchestration
    - decision-making
    - ui-ux
    - planning
    - synthesis
  status: draft
  side_effects: none
---

# Creative Direction Orchestrator

## Purpose

Coordinate a structured council of specialist design skills to solve broad, ambiguous, or high-impact digital design problems.

Produce decision artifacts and implementation plans only; do not implement frontend code.

Use the specialist roles to generate independent perspectives, expose conflicts, test assumptions, and produce one coherent recommendation.

The orchestrator is responsible for:

* framing the problem
* selecting the appropriate specialists
* controlling the order of analysis
* preventing groupthink
* identifying genuine disagreements
* resolving tradeoffs
* synthesizing one direction
* defining phased implementation
* preserving unresolved questions honestly

The orchestrator must not merely concatenate specialist outputs.

The result should feel like one senior creative and technical team reached a decision together.

## Specialist council

The primary council contains:

### `provocative-concept-director`

Owns:

* unexpected conceptual territories
* central premises
* creative tensions
* anti-generic thinking
* early concept selection

Primary question:

> What unexpected but relevant idea should govern the experience?

### `experimental-web-art-director`

Owns:

* visual and emotional art direction
* expressive composition
* signature visual moments
* creative ambition
* memorable experience qualities

Primary question:

> How can the selected idea become visually unmistakable?

### `minimalist-brand-director`

Owns:

* brand compression
* signal-to-noise reduction
* restraint
* recognition
* system consistency

Primary question:

> What can be removed, and which signals must remain distinctive?

### `editorial-digital-designer`

Owns:

* content hierarchy
* typography
* composition
* image sequencing
* page pacing
* responsive editorial structure

Primary question:

> How should the content be organized and experienced?

### `conversion-creative-director`

Owns:

* audience decision path
* offer clarity
* trust
* proof
* objection handling
* calls to action
* commercial action

Primary question:

> How does the experience help the right visitor understand, trust, and act?

### `motion-experience-director`

Owns:

* motion hierarchy
* feedback
* transitions
* pacing
* interruption
* reduced-motion behavior

Primary question:

> How should the experience behave over time?

### `creative-technologist`

Owns:

* browser feasibility
* architecture
* rendering choices
* progressive enhancement
* technical risk
* performance
* implementation phases

Primary question:

> How can the essential concept survive production in a real browser?

## Skill invocation behavior

When the environment supports invoking named skills:

1. Invoke the selected skills individually.
2. Give each skill the same problem frame and relevant evidence.
3. Keep the first specialist round independent.
4. Collect structured outputs before beginning synthesis.

When direct skill invocation is unavailable:

1. Locate the specialist `SKILL.md` files through the available skill registry or repository.
2. Read the relevant workflows.
3. Apply each selected workflow as a separate analytical pass.
4. Keep the specialist positions clearly separated.
5. Do not claim that unavailable skills were invoked.

Expected repository paths include:

```txt
skills/ui-ux-polish/provocative-concept-director/SKILL.md
skills/ui-ux-polish/experimental-web-art-director/SKILL.md
skills/ui-ux-polish/minimalist-brand-director/SKILL.md
skills/ui-ux-polish/editorial-digital-designer/SKILL.md
skills/ui-ux-polish/conversion-creative-director/SKILL.md
skills/ui-ux-polish/motion-experience-director/SKILL.md
skills/ui-ux-polish/creative-technologist/SKILL.md
```

If a required skill is unavailable:

* mark it as unavailable
* continue with the available council
* identify which perspective remains unverified
* do not fabricate that specialist’s conclusions

## When to use this skill

Use this skill when:

* The user asks to design or redesign a website, homepage, landing page, product experience, campaign, portfolio, or major interface.
* The problem is broad enough to involve several competing design priorities.
* A project needs both creative ambition and production feasibility.
* The user wants multiple expert perspectives before choosing a direction.
* A page must balance brand, content, conversion, motion, and technical concerns.
* Existing design proposals conflict with one another.
* A design feels generic but the correct replacement is unclear.
* A creative concept needs to be challenged before implementation.
* A redesign needs a unified direction and implementation roadmap.
* The user asks for a design discussion, council, debate, workshop, critique, or multidisciplinary review.
* A team needs a decision rather than another collection of ideas.
* A flagship page justifies deeper analysis.
* A project is expensive or risky enough that premature implementation should be avoided.

Do not use this skill when:

* One specialist skill clearly covers the request.
* The user needs a small UI correction.
* The task is implementation of an already approved design.
* The request is purely technical debugging.
* The user only needs copywriting.
* The user only needs an accessibility audit.
* The task concerns one isolated component.
* The user wants rapid brainstorming without evaluation or synthesis.
* There is insufficient project context and no useful assumptions can be made.

## Council modes

Choose the smallest useful council.

### Focused council

Use three or four specialists for a narrowly defined problem.

Examples:

#### Concept and differentiation

* `provocative-concept-director`
* `experimental-web-art-director`
* `minimalist-brand-director`
* `creative-technologist`

#### Commercial homepage

* `conversion-creative-director`
* `editorial-digital-designer`
* `experimental-web-art-director`
* `creative-technologist`

#### Motion-led experience

* `motion-experience-director`
* `experimental-web-art-director`
* `creative-technologist`
* `editorial-digital-designer`

#### Brand simplification

* `minimalist-brand-director`
* `editorial-digital-designer`
* `conversion-creative-director`

### Full council

Use all seven specialists when:

* creating a new flagship experience
* redesigning an entire homepage
* resolving several competing goals
* the problem is highly ambiguous
* the user explicitly requests all perspectives
* commercial, brand, content, motion, and technical decisions are tightly connected

### Audit council

Use relevant specialists to review an existing design.

The council should:

* identify confirmed issues
* distinguish evidence from assumptions
* avoid redesigning everything automatically
* recommend the smallest coherent direction

### Concept council

Use before interface design begins.

Start with:

1. `provocative-concept-director`
2. `conversion-creative-director`
3. `minimalist-brand-director`
4. `experimental-web-art-director`
5. `creative-technologist`

Bring editorial and motion specialists in after a concept survives the first evaluation.

### Implementation-planning council

Use when the creative direction is already approved.

Prioritize:

1. `editorial-digital-designer`
2. `motion-experience-director`
3. `creative-technologist`
4. `conversion-creative-director`

Do not reopen the entire concept without material evidence.

## Inputs to inspect

Inspect the smallest relevant set of inputs.

### Project context

* project purpose
* target audience
* primary user action
* business objective
* brand position
* existing design
* required content
* success criteria
* fixed constraints
* timeline
* implementation budget

### Design evidence

* screenshots
* recordings
* wireframes
* prototypes
* current website
* content inventory
* design tokens
* typography
* imagery
* motion examples
* component inventory
* reference sites supplied by the user

### Technical evidence

* framework
* rendering model
* repository structure
* current dependencies
* browser requirements
* accessibility requirements
* performance constraints
* content-management model
* deployment model
* available frontend capabilities

### Existing specialist work

Inspect available outputs from:

* concept direction
* art direction
* editorial direction
* conversion strategy
* motion direction
* technical feasibility
* accessibility reviews
* design-system guidance

Do not make a specialist repeat work already completed unless the assumptions have changed.

## Council rules

### Independent first round

Each specialist must produce its initial position without adapting it to the other specialists.

This reduces premature consensus and groupthink.

Each position must contain:

* primary recommendation
* strongest reason
* non-negotiable requirement
* assumption being challenged
* primary risk
* concession or simplification it would accept

### No theatrical roleplay

Do not write fictional conversations such as:

> The art director leans forward and says...

Return structured positions and critiques.

The council is a decision method, not entertainment.

### Evidence before authority

A specialist position is not correct merely because it belongs to a named role.

Every important recommendation must connect to:

* project evidence
* user objective
* content
* business constraint
* accessibility requirement
* technical constraint
* clearly marked inference

### Disagreement is useful

Do not force agreement.

Identify disagreements such as:

* expressiveness versus clarity
* restraint versus memorability
* conversion emphasis versus brand tone
* editorial pacing versus page length
* motion ambition versus performance
* desktop spectacle versus mobile resilience
* custom interaction versus maintainability

### Synthesis is not averaging

Do not combine every preferred idea.

Select one dominant direction.

Supporting ideas may be included only when they reinforce that direction.

### No specialist has unlimited veto power

A specialist may issue a blocking concern only when:

* core content becomes inaccessible
* the primary action becomes unusable
* the concept depends on fabricated evidence
* the technical premise is not realistically deliverable
* the experience creates material legal or ethical risk
* the design cannot preserve its meaning through an accessible equivalent

A specialist must accompany a block with an alternative that protects the original objective.

### Preserve user priorities

The council may challenge the user’s assumptions, but it must not replace the user’s actual objective with its preferred kind of design.

## Decision hierarchy

Resolve conflicts in this order:

1. User objective and fixed constraints
2. Truthfulness, legality, accessibility, and user autonomy
3. Core content and primary action
4. Audience comprehension and trust
5. Brand distinction and conceptual integrity
6. Responsive and technical feasibility
7. Motion, visual effects, and secondary polish

A lower-level concern must not override a higher-level requirement without evidence.

## Workflow

### 1. Frame the problem

Create a shared problem frame containing:

* project
* audience
* primary message
* primary action
* current problem
* desired outcome
* available evidence
* fixed constraints
* open assumptions
* excluded work

Write one central design question.

Example:

> How can this technical portfolio feel experimental and memorable while keeping project evidence easy to scan and maintaining a realistic Astro implementation?

### 2. Determine whether a council is justified

Use a council when the problem contains at least two material tensions.

Examples:

* creativity and conversion
* expression and accessibility
* motion and performance
* minimalism and distinction
* editorial depth and scanning
* brand ambition and implementation budget

If one specialist can answer the problem adequately, route to that specialist instead.

### 3. Select the council

List:

* selected specialists
* reason each is included
* specialists intentionally excluded
* council mode
* expected decision

Do not invoke every skill by default.

### 4. Establish decision criteria

Choose criteria relevant to the task.

Possible criteria:

* strategic fit
* audience relevance
* distinctiveness
* comprehension
* content fit
* brand recognition
* conversion support
* accessibility resilience
* mobile resilience
* technical feasibility
* performance
* maintainability
* implementation cost
* future extensibility

Assign each criterion:

* critical
* important
* supporting

Avoid arbitrary numerical weighting unless the user requests it.

### 5. Run the independent specialist round

Give each selected skill:

* identical problem frame
* relevant evidence
* fixed constraints
* required output structure

Require:

* recommendation
* challenge
* non-negotiable
* risk
* acceptable compromise

Do not expose other positions during this round.

### 6. Normalize the positions

Convert specialist outputs into a common structure.

For each position, record:

* proposed direction
* project evidence
* value created
* requirement
* risk
* cost
* conflict with other priorities
* fallback

Remove repeated explanation without erasing meaningful disagreement.

### 7. Build the conflict map

Identify:

* direct conflicts
* compatible differences
* hidden assumptions
* shared principles
* unresolved questions

Classify each conflict as:

* strategic
* brand
* content
* conversion
* interaction
* motion
* accessibility
* technical
* production

### 8. Run cross-examination

Ask each relevant specialist to challenge no more than two material positions.

A challenge must state:

* disputed recommendation
* evidence or principle in conflict
* likely consequence
* possible resolution

Do not allow general statements such as:

> This might hurt usability.

Require the specific usability path or affected decision.

### 9. Identify the non-negotiables

Create one shared list containing only requirements necessary to protect:

* project objective
* user comprehension
* primary action
* brand recognition
* accessibility
* technical viability

Do not turn every specialist preference into a non-negotiable.

### 10. Generate candidate syntheses

Create up to three coherent combined directions:

#### Recommended direction

Best balance of the critical criteria.

#### Credible alternative

A materially different but viable direction.

#### Experimental wildcard

Include only when the project can support higher risk.

Each candidate must have:

* one central premise
* content implication
* visual implication
* conversion implication
* motion implication
* technical implication
* primary risk

Do not create hybrid directions by accumulating all specialist ideas.

### 11. Evaluate the candidates

Compare the candidates against the established criteria.

Use:

* strong
* acceptable
* weak
* unverified

Explain the most important tradeoffs.

Do not create false precision.

### 12. Select one direction

Choose one recommendation.

State:

* why it wins
* what it preserves
* what it sacrifices
* why rejected ideas were excluded
* what remains uncertain
* what must be tested

Do not return several equal recommendations when the task requests a decision.

### 13. Run the coherence test

Check whether the selected direction gives consistent answers for:

* homepage or page structure
* content hierarchy
* typography
* imagery
* brand expression
* conversion action
* interaction
* motion
* responsive behavior
* technical implementation

If different parts imply incompatible experiences, revise the synthesis.

### 14. Run the subtraction test

Ask:

* Which proposed sections are unnecessary?
* Which interactions repeat the same idea?
* Which visual treatments compete?
* Which motion patterns add no meaning?
* Which technical layers are optional?
* Which calls to action are redundant?

A council should reduce confusion, not produce a larger backlog of effects.

### 15. Run the accessible-baseline test

Ensure that the selected direction remains coherent through:

* semantic HTML
* keyboard interaction
* touch
* zoom and reflow
* reduced motion
* linear reading order
* unavailable advanced rendering
* failed JavaScript enhancement

Do not call a concept resolved when its essential meaning depends on an inaccessible mechanism.

### 16. Run the feasibility gate

The `creative-technologist` should classify the direction as:

* feasible
* feasible with constraints
* prototype required
* not production-feasible as proposed
* insufficient information

A constrained or negative verdict must include a simpler alternative that protects the essential concept.

### 17. Produce the unified creative brief

The unified brief must contain:

* direction name
* one-sentence premise
* audience
* experience objective
* brand character
* page or journey arc
* content hierarchy
* conversion hierarchy
* visual principles
* editorial principles
* motion principles
* technical principles
* accessibility baseline
* forbidden patterns
* signature moments
* responsive interpretation

This is the council’s main decision artifact.

### 18. Produce the implementation plan

Organize work into phases.

Recommended phases:

#### Phase 1: Foundation

* content
* semantic structure
* page hierarchy
* primary action
* responsive baseline

#### Phase 2: Visual system

* typography
* composition
* color
* imagery
* brand signals
* core components

#### Phase 3: Interaction system

* states
* feedback
* navigation
* forms
* conversion paths

#### Phase 4: Expressive layer

* motion
* transitions
* signature interactions
* advanced composition

#### Phase 5: Technical enhancement

* specialist rendering
* optional immersive effects
* progressive enhancements

#### Phase 6: Validation

* accessibility
* browser behavior
* responsive behavior
* performance
* content resilience
* conversion path
* motion and reduced motion

Do not start implementation with the most visually impressive feature.

### 19. Assign specialist ownership

For each phase, identify:

* leading specialist
* supporting specialists
* expected output
* validation gate

This keeps later work aligned with the council decision.

### 20. Record rejected directions

Record:

* rejected idea
* why it was rejected
* what condition could make it viable later

This prevents discarded ideas from quietly returning during implementation.

### 21. Define validation checkpoints

Include checkpoints after:

* concept approval
* page-arc approval
* visual-system approval
* interaction approval
* technical prototype
* implementation
* final QA

Each checkpoint should state:

* evidence required
* decision being made
* responsible role
* pass criteria

## Output format

Return:

```md
# Creative Direction Council: [Project]

## Problem frame

- Project:
- Audience:
- Primary message:
- Primary action:
- Current problem:
- Desired outcome:
- Fixed constraints:
- Unverified assumptions:

## Central design question

[One sentence]

## Council selection

| Specialist | Included | Reason |
|---|---:|---|

## Decision criteria

| Criterion | Priority | Reason |
|---|---|---|

## Independent positions

### [Specialist]

- Recommendation:
- Strongest reason:
- Non-negotiable:
- Assumption challenged:
- Primary risk:
- Acceptable compromise:

## Shared principles

- ...

## Conflict map

| Conflict | Positions | Consequence | Resolution |
|---|---|---|---|

## Candidate directions

### 1. [Direction]

- Premise:
- Strength:
- Sacrifice:
- Content implication:
- Visual implication:
- Conversion implication:
- Motion implication:
- Technical implication:
- Risk:

## Candidate evaluation

| Direction | Strategic fit | Distinctiveness | Clarity | Conversion | Accessibility | Feasibility |
|---|---|---|---|---|---|---|

## Final recommendation

- Selected direction:
- Why it wins:
- What it preserves:
- What it sacrifices:
- Remaining uncertainty:
- Required prototype or validation:

## Unified creative brief

### Premise

...

### Experience objective

...

### Brand and visual direction

...

### Editorial and content direction

...

### Conversion direction

...

### Motion direction

...

### Technical direction

...

### Accessibility baseline

...

### Signature moments

1. ...
2. ...

### Forbidden patterns

- ...

## Sections or ideas to remove

- ...

## Implementation phases

| Phase | Objective | Lead specialist | Outputs | Validation gate |
|---|---|---|---|---|

## Rejected directions

| Direction | Reason rejected | Reconsider when |
|---|---|---|

## Open decisions

- ...

## Council validation

- [ ] The problem is framed before solutions are proposed.
- [ ] The smallest useful council was selected.
- [ ] Initial specialist positions were independent.
- [ ] Meaningful disagreements are preserved.
- [ ] Recommendations cite project evidence or marked assumptions.
- [ ] One direction is clearly selected.
- [ ] The result is a coherent direction rather than a collection of ideas.
- [ ] Accessibility and user autonomy are protected.
- [ ] The primary action remains understandable.
- [ ] Mobile and reduced-motion interpretations are defined.
- [ ] Technical uncertainty is marked.
- [ ] High-risk ideas have prototypes or fallbacks.
- [ ] Rejected directions are recorded.
- [ ] Implementation begins with foundations.
```

## Quality bar

The task is complete only when:

* A council is used only when multiple perspectives are materially useful.
* The problem frame is shared across specialists.
* Selected specialists have explicit reasons for inclusion.
* Initial positions are developed independently.
* Specialist recommendations are normalized into a common structure.
* Conflicts are identified rather than hidden.
* Critiques identify specific consequences.
* The orchestrator does not average incompatible ideas.
* One dominant direction is selected.
* The recommendation is grounded in the user’s objective.
* The final direction remains conceptually coherent.
* The primary action and audience comprehension are protected.
* Accessibility and truthfulness have priority over spectacle.
* Technical feasibility shapes but does not automatically flatten the concept.
* Optional spectacle is separated from essential experience.
* Sections, effects, and components to remove are identified.
* A unified creative brief is returned.
* Implementation phases and ownership are explicit.
* Rejected directions and open questions are recorded.
* Unavailable specialist skills are reported honestly.
* No implementation, testing, or validation is claimed unless performed.

## Edge cases

### All specialists agree immediately

Check for:

* weak problem framing
* generic recommendations
* missing constraints
* premature consensus

Ask at least one specialist to challenge the shared assumption.

### Specialists strongly disagree

Identify whether the conflict comes from:

* different audience assumptions
* different business priorities
* different risk tolerance
* missing content
* unclear constraints

Resolve the underlying assumption before choosing a design direction.

### The user explicitly requests every specialist

Use the full council, but keep each contribution focused.

Do not return seven complete redesigns.

### One specialist is irrelevant

Include it only if the user explicitly requested the full council.

Mark its influence as limited rather than forcing artificial recommendations.

### A specialist skill is unavailable

Continue with available roles.

Mark the missing perspective and relevant validation as unverified.

### Conversion conflicts with brand restraint

Prioritize clarity and action without automatically increasing visual intensity.

Use:

* specific CTA labels
* better placement
* stronger evidence
* clearer next steps
* reduced competition

rather than louder styling by default.

### Experimental art direction conflicts with accessibility

Preserve the underlying premise.

Replace the inaccessible mechanism with an equivalent semantic, keyboard, touch, or reduced-motion expression.

### Motion conflicts with performance

Identify the meaning carried by the motion.

Preserve that meaning using a simpler transition, static sequence, media fallback, or reduced enhancement tier.

### Technical feasibility is uncertain

Require a focused prototype.

Do not approve full implementation based on speculation.

### The user wants only ideas

Use the concept council and stop before the implementation plan.

### The direction is already approved

Use implementation-planning mode.

Do not reopen settled creative decisions without material evidence.

### The task is small

Route directly to the most relevant specialist.

Do not convene a design parliament to adjust one button.

## Related skills

* `provocative-concept-director`
* `experimental-web-art-director`
* `minimalist-brand-director`
* `editorial-digital-designer`
* `conversion-creative-director`
* `motion-experience-director`
* `creative-technologist`
* `plan-ui-ux`
* `visual-quality-review`
* `accessible-interaction-review`
