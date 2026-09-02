# Expressive Grid Strategy Guide

Read this reference when an `expressive-grid-planner` task needs detailed grid-family selection prompts, structural notation, responsive tests, strategy examples, or anti-pattern diagnosis.

## Grid-family selection

### Simple and even-column structures

Start with a single field or two, three, four, six, eight, or twelve columns when repeated content, implementation simplicity, and shared alignment dominate.

Ask:

```txt
Which useful text, image, and mixed-content widths does this enable?
Can important relationships be expressed without another grid?
Can spans and empty columns create enough variation?
```

Column count is a consequence, not a thesis.

### Asymmetric structures

Use unequal relationships such as `1:2`, `2:3`, `3:5`, `1:3`, or a narrow annotation rail beside a wider content field when hierarchy benefits from unequal space.

Document:

```txt
Dominant field:
Supporting field:
Persistent empty field:
Shared anchors:
Reason for asymmetry:
Risk at narrower sizes:
```

Asymmetry should create hierarchy, directional flow, useful tension, or annotation space—not novelty alone.

### Ratio-based structures

Derive ratios from meaningful product proportions, brand geometry, image formats, visual-system principles, or content hierarchy. Mathematical purity is unnecessary. A golden ratio or Fibonacci sequence is a tool, not evidence of quality.

### Modular grids

Add horizontal fields when image depth, section rhythm, captions, repeated content, or vertical relationships need coordination. Intersections of columns and fields create modules for images, text depth, quotes, captions, pauses, or diagrams.

Modules support placement choices; they do not require every element to fill an exact cell.

### Nested grids

Use a local sub-grid when one region, such as data, a gallery, or product collection, requires denser alignment than the surrounding page. Preserve clear containment and shared edges so the local structure remains related to the primary grid.

### Compound grids

Combine structures when content types have incompatible needs—for example, a six-column editorial system plus a four-column product system.

Record:

```txt
Primary grid:
Secondary grid:
Content assigned to each:
Shared outer margins:
Shared center line or axes:
Shared horizontal fields or baseline:
Reason one grid is insufficient:
```

Use the fewest compatible structures that create useful variability.

## Compositional behavior

### Whitespace

Whitespace may separate ideas, isolate emphasis, pace a chapter, improve readability, balance dense content, or support asymmetry. Record important empty fields intentionally.

```txt
Empty field:
When it remains empty:
What may enter it:
Purpose:
Responsive behavior:
```

### Density and rhythm

Describe page rhythm as a sequence rather than identical section padding:

```txt
dense -> open -> dense
quiet -> build -> focal moment -> release
claim -> evidence -> pause -> action
```

### Balance and tension

Visual weight comes from size, color, imagery, density, contrast, texture, typography, and motion. Identify the center of gravity. Symmetry is not required for balance.

Use stability for trust, clarity, technical explanation, or transactional areas. Use controlled tension for editorial moments, transformation, confrontation, or campaign emphasis.

### Structural exceptions

Possible exceptions include full bleed, overlap, entering an empty column, bridging grids, breaking a horizontal field, or extending beyond an edge.

```txt
Element:
Normal behavior:
Exception:
Reason:
Expected effect:
Responsive fallback:
Risk:
```

An exception works only when enough underlying structure remains visible.

## Structural notation

Use lightweight text diagrams only to communicate proportion, hierarchy, or relationship.

```txt
| annotation |------------- main content -------------|

               DOMINANT IMAGE
               DOMINANT IMAGE

CHAPTER        heading
MARKER         explanation
```

```txt
|---------- evidence image ----------|--- claim ---|
|---------- evidence image ----------|-------------|
|--- stat ---|--- stat ---|---------- action -------|
```

Avoid pixel values, exact breakpoints, or diagrams that imply a finished mockup.

## Responsive transformation test

First name the relationships that must survive:

```txt
Dominance:
Sequence:
Pairings:
Contrasts:
Annotations:
Primary action:
```

Then plan:

| Behavior | Wide | Medium | Narrow |
|---|---|---|---|
| Primary structure | | | |
| Secondary structure | | | |
| Dominant content | | | |
| Empty fields | | | |
| Captions and annotations | | | |
| Structural exceptions | | | |
| Source order | | | |

Medium often needs its own composition. On narrow screens, preserve hierarchy through indentation, alternating alignment, variable image width, chapter markers, controlled negative space, or type-scale contrast rather than an automatic full-width stack.

Visual placement may differ from document order, but semantic order must remain logical for screen readers, keyboard users, zoom, and CSS-disabled contexts.

## Content and resilience tests

For each direction, test:

- A headline twice as long.
- Translation or text expansion of roughly 30%.
- A longer quote or testimonial.
- Portrait imagery replacing landscape imagery.
- Missing optional images or sections.
- One statistic instead of several.
- Repeated groups of three, six, and eleven items.
- Larger text and browser zoom.
- Narrow reflow without two-dimensional scrolling for normal text.
- CMS choices an editor can realistically make.

The structure should not depend on exact line counts or artificial filler.

## Strategy examples

These are reasoning patterns, not templates.

### Asymmetric editorial

```txt
content: large project imagery + short editorial copy + captions
need: strong image hierarchy without losing context
structure: six columns with one or two frequently empty fields
effect: tension, annotation space, and varied image scale
```

### Compound commerce

```txt
content: editorial storytelling + repeatable product collections
need: expressive narrative + predictable commerce
structure: six-column editorial grid + four-column product grid
anchors: shared outer margins and selected vertical axes
```

### Process grid

```txt
content: stages with different amounts of evidence
need: sequence + controlled variation
structure: modular columns and horizontal stage fields
effect: stages remain related while their visual weight varies
```

### Dense information grid

```txt
content: statistics + diagrams + annotations + body copy
need: density without flat hierarchy
structure: compound modular grid
effect: dominant evidence plus aligned supporting detail
```

## Anti-patterns

### Default twelve

Do not choose twelve columns simply because a grid is required. Begin with relationships and useful widths.

### Grid cosplay

Reject complicated diagrams that do not materially affect composition, hierarchy, or authoring.

### Golden-ratio mythology

Do not claim that a mathematical ratio makes a composition inherently beautiful.

### Asymmetry for aesthetics

Off-center placement needs a purpose: hierarchy, movement, tension, useful space, or concept expression.

### Mandatory grid break

Do not require an overlap or escape in every section. Structural violations must remain exceptions.

### Desktop masterpiece, mobile spreadsheet

Do not preserve desktop drama by reducing narrow layouts to an undifferentiated full-width stack. Transform relationships deliberately.

### Component-led composition

Do not sequence hero, feature, card, testimonial, and CTA components and call the result a layout system. Start with content roles and relationships.

### Same-layout repetition

One grid should generate multiple compositions. Repeating a single section template is not a flexible grid system.

### Meaningless empty space

Whitespace must improve hierarchy, rhythm, focus, pacing, or readability; otherwise it may simply waste space.

