# Art-Direction Coherence Evaluation Framework

Read this reference when performing `art-direction-coherence-review`. Select only the lenses supported by the supplied evidence; do not manufacture findings to complete every section.

## Meaning alignment

Compare intended and perceived meaning:

| Dimension | Intended | Perceived | Alignment |
|---|---|---|---|
| Core idea | | | |
| Personality | | | |
| Emotional tone | | | |
| Value proposition | | | |
| Audience relationship | | | |
| Trust level | | | |

Use `supports`, `partially supports`, `neutral`, `contradicts`, or `unverified`.

Identify the dominant signal—often typography, hero imagery, color, motion, layout, language, a graphic device, or an interaction—and ask:

- Is this signal supposed to dominate?
- Does it support the concept?
- Does it overpower more important information?

## Content and narrative

### Message hierarchy

Check whether:

- The opening establishes the intended idea.
- The primary message is clear.
- Claims connect to proof.
- Sections build a meaningful progression.
- CTAs appear at an appropriate narrative point.
- Features connect to outcomes rather than becoming a generic inventory.
- The concept survives below the hero rather than collapsing into default feature, testimonial, and CTA blocks.

### Content-form relationships

For each important treatment, ask why the content is presented that way. Examples include an oversized quote, isolated statistic, full-bleed image, sequential process, or unusually large whitespace. A strong answer should arise from the content, hierarchy, or concept—not merely taste.

## Voice and microcopy

Compare headlines, body copy, labels, CTAs, navigation, forms, empty states, and utility language.

Ask:

- Do they sound like the same organization?
- Does language reinforce the concept or become generic in functional areas?
- Does playful language appear where seriousness is required?
- Does formal language contradict an otherwise human direction?
- If the strongest headline disappeared, would the rest of the experience still express the concept?

## Typography

Review typography as meaning, not decoration.

Consider scale, weight, spacing, position, contrast, rhythm, case, density, and alignment. Ask:

- What personality does the type communicate?
- Does hierarchy match the narrative?
- Do display treatments have a conceptual reason?
- Does body typography preserve readability?
- Are captions, quotes, metadata, and labels intentionally differentiated?
- Does the system contribute beyond “large heading plus small paragraph”?

For extreme scale, rotation, overlap, unusual alignment, deconstructed words, vertical labels, or edge cropping, ask whether the exception reinforces the content, behaves systematically enough to feel intentional, and preserves comprehension.

## Imagery

Classify each major image as `evidence`, `narrative`, `atmosphere`, `product`, `identity`, or `decoration`.

Then review:

- Whether the role is clear and supports the concept
- Whether imagery feels specific to the project
- Whether image styles relate without requiring one universal treatment
- Whether real product or process evidence has been displaced by generic stock or synthetic imagery
- Whether photography and typography communicate compatible personalities
- Whether crop, scale, distance, light, color, subject, context, and sequencing respond to each image's role

## Visual-system behavior

### Principles

For each documented principle, record:

| Principle | Evidence | Alignment | Notes |
|---|---|---|---|

Ask whether the principle is visible, missing where useful, overused, or applied literally instead of conceptually.

### Invariants

Check whether essential signals remain recognizable, such as framing behavior, scale relationships, image behavior, compositional logic, signature motion, or a recurring graphic atom. Random changes to invariants weaken coherence.

### Variables

Check whether variations in density, composition, image treatment, device use, or expression level respond to content, hierarchy, narrative, task, channel, or context. Variation without a reason is noise; variation with a reason may strengthen coherence.

## Expression balance

Classify major sections as `quiet`, `standard`, or `expressive`.

Ask:

- Are expressive moments reserved for meaningful moments?
- Are quiet areas permitted to remain quiet?
- Is the whole experience operating at maximum intensity?
- Does functional content receive unnecessary treatment?
- For each expressive peak: why here, why this treatment, what changes in understanding, and does the intensity match narrative importance?

Protect strong signature moments when they have a reason. Do not flatten a design merely to increase uniformity.

## Composition and spatial hierarchy

Review whether composition reinforces importance, sequence, relationships, contrast, tension, and pacing.

Ask:

- What is seen first and second, and why?
- Does that sequence match the content hierarchy?
- Do varied sections retain structural DNA through margins, axes, grids, fields, framing, or whitespace relationships?
- Do overlaps, bleeds, offsets, and grid escapes break a perceivable rule for a meaningful reason?

Route microscopic alignment, spacing, balance, proportion, rhythm, and grid craft to `layout-principles-review`.

## Motion

Record the recurring motion verbs, such as `fade`, `slide`, `rotate`, `focus`, `assemble`, `expand`, `compress`, `reveal`, `track`, `scatter`, or `snap`. Compare this vocabulary with the concept, visual system, product behavior, and narrative.

Classify motion as `functional`, `narrative`, `signature`, or `decorative`, then ask:

- Does it explain change or progression?
- Is signature motion selective?
- Are unrelated animation styles competing?
- Is motion present only because a library supports it?
- Do simultaneous effects, constant movement, excessive scroll triggers, or repetitive reveals erase hierarchy?

## Interaction

Review hover, pointer and touch behavior, navigation, filtering, reveals, scrolling, and transitions.

Ask:

- Does interaction behave like the same brand and concept?
- What value does each unusual interaction add?
- Can users understand or complete the task without discovering a hidden interaction?
- Are ordinary controls made unconventional without a meaningful benefit?

Decorative discovery may remain optional. Essential information and actions must not depend on it.

## Generic fallback and concept drift

Look for places where the project abandons its direction for common defaults: generic SaaS cards, testimonial carousels, logo clouds, CTA blocks, glass effects, dark gradients, icon grids, or unrelated trendy devices.

The issue is not the presence of a convention. Ask whether the project stopped expressing its own direction there.

Run the local substitution test:

1. Mentally remove the logo, company name, and product name.
2. Ask whether the section still belongs with the rest of the experience.
3. Ask whether it could be inserted unchanged into an unrelated competitor site.

Do not demand that utility elements become distinctive. Flag substitution only when it weakens the concept.

Name drift as a transition, for example:

```txt
quiet editorial system → excessive scroll effects
precise technical identity → playful utility copy
human documentary concept → synthetic abstract imagery
flexible system → every device used in every section
```

## Cross-layer contradictions

Record contradictions directly:

| Layer A | Layer B | Contradiction | User effect |
|---|---|---|---|

Examples include authoritative copy with cartoon-like typography, a transparent-process concept with hidden process evidence, a quiet-precision system with elastic motion, or a tactile brand with generic glossy imagery.

Contradictions often matter more than isolated weak choices.

## Over-direction

List the major techniques in use and classify each as `essential`, `supporting`, `decorative`, or `unrelated`. Techniques may include oversized type, grain, 3D, parallax, scroll reveals, cursor effects, irregular grids, kinetic type, masks, gradients, or floating cards.

Remove unrelated techniques first. If a metaphor is used, check whether literal repetition turns recognition into parody. A design in which everything shouts has no emphasis.

## Under-direction

Look for default sections, inconsistent imagery, generic UI, missing project-specific signals, timid hierarchy, absent narrative progression, or no meaningful variation. Strengthen existing principles before inventing new ones.

## Responsive coherence

Across viewports, record what survives, disappears, and changes. Ask whether hierarchy and personality remain.

Review transformation rather than fidelity. A desktop parallel composition may become alternating views on mobile; a large annotation field may become inline annotation. Different execution can preserve the same art direction.

## Accessibility and usability

Check whether expressive devices interfere with reading order, contrast, type legibility, zoom, keyboard operation, touch, reduced motion, or comprehension.

Do not immediately remove an expressive idea. Identify its underlying principle and find a safer expression when possible. For example:

```txt
principle: transformation
problematic execution: mandatory scroll animation
safer expression: static before/after states plus optional animation
```

Preserve familiar behavior where familiarity helps. Art direction may shape presentation, tone, hierarchy, and character, but it should not obscure navigation, buttons, forms, pricing, purchase actions, or critical product information.

## Performance proportionality

When implementation evidence exists, ask whether high-cost video, real-time 3D, canvas effects, font payloads, media, or scroll animation provides conceptually central value. This is not a technical performance audit; route measurement and optimization to a specialist.

## Strength preservation

Before proposing changes, identify:

- The strongest expression of the concept
- The strongest application of the visual system
- The strongest content-form relationship
- The strongest signature moment
- The strongest responsive adaptation

Mark these `preserve` so refinement does not erase effective work.

## Priority model

- **Critical:** The execution contradicts the intended meaning or makes important content unusable.
- **High:** The issue substantially weakens coherence across major parts of the experience.
- **Medium:** The issue creates local inconsistency or unnecessary noise.
- **Low:** The issue is refinement rather than conceptual repair.

Do not label subjective preferences as critical.

For each recommendation, state:

```txt
Problem:
Why it matters:
Concept principle:
Recommended correction:
Expected effect:
```

Prefer removing one unrelated effect over redesigning a section, reusing a system principle over inventing another device, and changing an image's role over replacing a sound art direction.

Avoid empty language such as “make it premium,” “make it pop,” “add visual interest,” or “make it cleaner.”

## Verdict definitions

- **Coherent:** Major layers reinforce one concept, and variation feels purposeful.
- **Mostly coherent:** The concept is strong, but several local areas drift or weaken it.
- **Fragmented:** Competing design ideas prevent a clear direction from emerging.
- **Concept drift:** The approved concept remains in early or isolated areas, but much of the execution has reverted to generic or unrelated patterns.
- **Over-directed:** The concept is visible but repeated so aggressively that the experience becomes noisy or theatrical.
- **Under-directed:** The execution is competent but insufficiently expresses the approved or inferred concept.
- **Insufficient evidence:** The supplied material cannot support a reliable overall verdict.

Do not use a numerical score as the primary verdict unless the user explicitly asks for one.

## Anti-patterns

- **Pixel-police review:** Do not reduce art direction to local measurements.
- **Consistency obsession:** Do not make sections alike merely because they differ.
- **Redesign reflex:** Preserve strong decisions instead of replacing them because another solution exists.
- **Taste as rationale:** Tie critique to concept, audience, content, hierarchy, system, or comprehension.
- **More-branding fix:** Do not automatically add a logo, color, pattern, or metaphor to a disconnected section.
- **Maximum-expression fix:** Do not spread a signature effect everywhere to create coherence.
- **Creativity-versus-accessibility framing:** Preserve the principle while changing an inaccessible technique.
