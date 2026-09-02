# Kinetic Continuity Pattern Catalog

Use this reference to select and tune a motion pattern. The defaults are derived from the shared qualities of nine source reference clips; they are starting points, not measurements of the source animations.

## Selection matrix

| Primitive | Use when | Spatial rule | Avoid when |
| --- | --- | --- | --- |
| Inertial field | Users explore a loose image constellation | The field carries one velocity; cards keep local orientation | Content needs fixed reading order or frequent precise selection |
| Parallel rails | Repeated media should imply breadth or abundance | Each rail owns one axis and a narrow speed range | Users must read every tile while it moves |
| Routed groups | Categories or clusters move between visible lanes | A group travels as a unit before internal stagger | The destination has no visible structural relationship |
| Anchored preview exchange | A list or index controls one preview region | Controls stay fixed while preview content changes in place | Every item needs simultaneous comparison |
| Curved procession | A sequence needs a focal item plus visible neighbors | Position, scale, opacity, and stack order share one progress value | A simple linear list communicates the sequence better |
| Converging chain | An overview becomes a featured composition | Scale follows distance to one focal destination | Items do not share identity across the two states |
| Contact-sheet resolve | A dense overview filters or expands into a curated state | Retained items bridge both layouts | A hard navigation boundary would be clearer |
| Bounded text disruption | Display typography needs one brief expressive accent | Distortion remains local and reconstructs the base state | Text is instructional, long-form, rapidly changing, or essential to task completion |

## Inertial field

- Connect the grabbed point directly to the pointer or finger.
- On release, project only a short distance from recent velocity and decelerate with `power3.out` or `power4.out`.
- Use soft resistance near real bounds. Snap only when discrete destinations exist.
- Keep decorative local rotations nearly fixed while the field travels.
- For looping fields, recycle offscreen content without changing source order or growing the DOM.
- Cancel momentum immediately when a new gesture begins.

Reduced motion: present a stable grid or native scroll region with no momentum or autoplay.

## Parallel rails

- Keep gaps and item geometry stable while rails move.
- Vary rail speed within roughly `0.85x–1.15x` of the base rate.
- Alternate direction only when the larger reading pattern remains clear.
- Pause when the user interacts with rail content.
- Avoid combining rail movement with independent card rotation or scale pulses.

Reduced motion: stop automatic movement and expose all content in a stable layout or overflow region.

## Routed groups

- Anchor travel to visible rows, rules, columns, or containers.
- Move the group first; add a small internal stagger only when it clarifies order.
- Overlap outgoing and incoming motion by approximately `25–40%`.
- Keep the control surface still so users retain an orientation anchor.
- Reuse the current rendered position when a route changes mid-transition.

Reduced motion: replace the group immediately or use an opacity transition no longer than `150ms`.

## Anchored preview exchange

- Keep the index, labels, and preview boundary stable.
- Use a crossfade, mask, or directional offset of about `12–28px`.
- Retarget from the current rendered state on rapid focus or hover changes.
- Never queue every transient hovered item.
- Use the same visual grammar for hover, focus, keyboard selection, and tap.

Reduced motion: replace the preview in place with no translation; an optional short crossfade is acceptable.

## Curved procession

- Represent each item's location with one normalized path progress value.
- Derive translation, scale, opacity, and stack order from that value.
- Slow visual change near the focal zone to improve recognition.
- Change stack order at stable crossing points to prevent flicker.
- During drag, follow the gesture directly; apply easing only to the release snap.
- Provide visible previous and next controls and optional arrow-key support.

Reduced motion: present discrete selection states without orbiting, inertia, or depth travel.

## Converging chain

- Begin with a legible spine, line, or cluster.
- Bend the path continuously instead of teleporting items between geometries.
- Couple scale to distance from the focal destination.
- Let the selected element arrive slightly before supporting elements.
- Resolve every essential element to rest.

Reduced motion: present the final focused composition immediately.

## Contact-sheet resolve

- Preserve recognizable retained items across both layouts.
- Use Flip or equivalent shared-element movement for retained items.
- Fade removed items only when their spatial destination would be misleading.
- Open empty space progressively instead of replacing the grid in one frame.
- Transform an inner scene layer rather than zooming the document or sticky owner.

Reduced motion: switch layouts without zoom or shared-element travel.

## Bounded text disruption

- Keep the semantic text intact and animate visual wrappers or decorative clones.
- Restrict displacement to horizontal slices or words.
- Disrupt for approximately `120–240ms`; reconstruct over `180–320ms`.
- Keep displacement below one body-text character width or about `8%` of a display line.
- Do not loop the effect or place it beside sustained reading.

Reduced motion: remove the effect entirely.

## Timing and easing

| Role | Duration | GSAP ease | CSS approximation |
| --- | ---: | --- | --- |
| Immediate acknowledgement | `90ms` | `power2.out` | `cubic-bezier(0.22, 1, 0.36, 1)` |
| Hover or focus | `180ms` | `power3.out` | `cubic-bezier(0.22, 1, 0.36, 1)` |
| Compact state change | `320ms` | `power3.out` | `cubic-bezier(0.22, 1, 0.36, 1)` |
| Layout reconfiguration | `520ms` | `power2.inOut` | `cubic-bezier(0.65, 0, 0.35, 1)` |
| Large spatial scene | `780ms` | `power4.out` | `cubic-bezier(0.16, 1, 0.3, 1)` |
| Exit phase | Shorter than entry | `power2.in` | `cubic-bezier(0.55, 0, 1, 0.45)` |
| Direct or scrubbed input | Input-controlled | `none` | `linear` |

Scale duration modestly with travel distance, but keep ordinary UI transitions below `1000ms`. Use `35ms` for tight staggers and up to `60ms` for larger spatial groups.

## Choreography recipe

1. Establish the stationary frame or control surface.
2. Respond to input on the next painted frame.
3. Move the selected or leading object first.
4. Move neighbors by their spatial distance from that leader.
5. Begin the incoming state before the outgoing state has fully resolved.
6. Decelerate into a crisp final composition.
7. Clear temporary promotion and stale inline state after one-off motion.

Staggers should describe space. Sequence from the edge that initiates travel, outward from a selected item, or inward toward a convergence point. Avoid DOM-order and random staggers when they contradict the visual geometry.

## Naturalness checks

- **Response:** Does direct input change the rendered state without perceptible lag?
- **Continuity:** Can the viewer identify the same object before, during, and after the change?
- **Direction:** Is there one dominant vector in each beat?
- **Energy:** Do neighboring objects share related velocity and timing?
- **Interruption:** Does new input retarget current motion without replaying stale states?
- **Settle:** Does the composition decelerate into a precise, readable state?
- **Rest:** Is there enough stillness to inspect the result?
- **Meaning:** Do scale, depth, opacity, and order communicate focus or state rather than decoration?

## Implementation checks

- Prefer transform and opacity.
- Cache layout and path geometry outside high-frequency callbacks.
- Keep one progress source for coupled path properties.
- Recycle offscreen items instead of extending the DOM indefinitely.
- Avoid persistent `will-change` across large collections.
- Stop continuous work when the document is hidden.
- Preserve useful static content if JavaScript fails.
- Verify the final state at responsive breakpoints before tuning intermediate frames.

## Accessibility checks

- Hover has focus and touch equivalents.
- Drag, wheel, and swipe have visible non-gesture alternatives.
- Focus remains visible and follows semantic source order.
- Split or disrupted text retains one readable semantic source.
- Reduced motion removes inertia, autoplay, orbiting, zoom travel, and text disruption.
- No essential content begins hidden or depends on animation completion.
- Accessibility claims are withheld until keyboard, screen-reader, zoom, contrast, and reduced-motion behavior are tested.
