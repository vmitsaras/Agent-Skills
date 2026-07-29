---
name: assistive-technology-test-plan
description: Creates a practical, risk-based assistive-technology testing plan for a website, application, component, or user flow. Use when the user needs representative browser and screen-reader combinations, keyboard-only, zoom or magnification, voice control, switch or alternative input, forced-colors coverage, test tasks, evidence requirements, and stopping criteria without testing every possible combination.
license: MIT
compatibility: Portable Agent Skill. Can be copied into an Agent Skills-compatible environment with access to product support information and testable interface details; execution may additionally require the named browsers, devices, assistive technologies, accounts, and fixtures.
metadata:
  category: project-planning
  task_type: planner
  audience: accessibility-testers-qa-leads-and-product-teams
  tags:
    - accessibility
    - assistive-technology
    - test-planning
    - screen-readers
    - keyboard
    - magnification
    - voice-control
    - alternative-input
    - forced-colors
  status: draft
  side_effects: none
---

# Assistive Technology Test Plan

## Purpose

Create an executable, proportionate assistive-technology test plan. Select representative environments from product support, user risk, audience evidence, interface patterns, and available equipment; define realistic tasks and reproducible protocols; and state exactly what the resulting evidence can and cannot establish.

This skill plans testing. It does not perform tests, remediate defects, certify legal compliance, or prove WCAG conformance. A result applies only to the tested target, version, state, data, browser, platform, assistive technology, settings, and task.

## When to use this skill

Use this skill when:

- A website, application, component, release, or user flow needs a focused assistive-technology test plan.
- A team must choose representative browsers, desktop or mobile screen readers, input methods, display adaptations, and user settings.
- Testers need tasks, setup, test data, expected behavior, observation prompts, evidence formats, and stopping criteria.
- Time or equipment constraints require defensible risk-based coverage rather than an exhaustive compatibility matrix.
- `inclusive-interface-audit-orchestrator` assigns an assistive-technology planning work package.

Do not use this skill when:

- The user wants a broad multi-framework audit plan; use `inclusive-interface-audit-orchestrator`.
- The user needs a full WCAG audit scope rather than an assistive-technology execution plan; use `wcag-audit-scope-planner`.
- The request is to execute tests, diagnose a specific defect, or implement fixes.
- The request is for participant research; expert assistive-technology testing is not a substitute for usability testing with disabled people.
- The user asks for a conformance statement based only on assistive-technology results.

## Operating rules

- Do not demand every browser and assistive-technology combination.
- Prioritize supported combinations, critical tasks, high-impact failures, known audience needs, common production environments, unique interaction patterns, and credible prior evidence.
- Prefer combinations documented by the product or organization. If support policy is missing, label proposed combinations as assumptions requiring confirmation.
- Do not infer one screen reader, browser, platform, input mode, or user setting from another.
- Do not treat successful task completion as proof of an optimal, efficient, or equivalent experience.
- Test with default assistive-technology settings first unless the product or scenario requires a documented customization. Record every non-default setting.
- Keep keyboard-only testing distinct from screen-reader testing. Screen readers can change keyboard interaction modes and do not replace a keyboard-only pass.
- Use generic capability labels when exact products are unknown; do not invent availability, market share, or audience evidence.
- Do not convert an observation into a WCAG failure unless a separate audit process maps sufficient evidence to a specific success criterion.
- Planning has no side effects. Do not create accounts, change production data, install software, or run tests unless separately authorized.

## Inputs to inspect

Start with the smallest useful evidence set:

- Target URL, build, component, route, flow, version, release decision, and test deadline.
- Product support policy for operating systems, browsers, devices, assistive technologies, and versions.
- Audience research, accessibility statements, analytics, support requests, prior defects, previous audits, and user feedback.
- Critical and frequent tasks, safety or financial consequences, legal or organizational obligations, and known failure-prone areas.
- Route, component, interaction, state, role, locale, viewport, and third-party-content inventories.
- Test environment access, accounts, permissions, feature flags, devices, software licenses, tester experience, and time budget.
- Stable test data and fixtures for success, error, empty, loading, timeout, permission, recovery, and destructive-action paths.
- Existing automated, source, manual, assistive-technology, and user-research evidence, including its date and limitations.

If key inputs are unavailable, record gaps and create a provisional plan with explicit assumptions. Do not silently turn assumptions into support requirements.

## Coverage model

Evaluate these modalities and select only justified coverage:

| Modality | Representative candidates | Select when |
|---|---|---|
| Browser baseline | Product-supported desktop and mobile browsers or rendering engines | Always select the browsers needed by chosen AT combinations and any materially different supported engine |
| Desktop screen reader | A supported combination on each priority desktop platform, such as a platform-integrated reader or a widely supported third-party reader | Reading, navigation, forms, custom controls, tables, dialogs, dynamic updates, or desktop workflows are in scope |
| Mobile screen reader | A platform-integrated reader on each supported priority mobile platform | Mobile use, touch exploration, responsive controls, gestures, virtual keyboards, or mobile-only flows are material |
| Keyboard only | Hardware keyboard with browser and platform conventions, without a screen reader | Any interactive content exists |
| Zoom and magnification | Browser zoom, text resize, OS magnifier, or platform zoom at justified settings | Dense layouts, responsive changes, persistent controls, hover content, precision, or low-vision use is relevant |
| Voice control | Supported platform speech control with visible names, numbers, grids, or product-specific commands as appropriate | Users must target, activate, dictate into, or navigate controls by speech |
| Switch or alternative input | Switch scanning, keyboard-emulating switch, on-screen keyboard, head pointer, eye gaze, or other supported input | Audience evidence, product support, motor-access risk, custom gestures, drag, timing, or precision makes it relevant |
| High contrast or forced colors | Supported OS high-contrast theme, browser forced-colors mode, or equivalent platform setting | Meaning depends on color, custom styling, focus indicators, icons, selected states, charts, or form controls |

Use product support, not this table's examples, to name exact products and versions. Where a modality is excluded, record the rationale, evidence, residual risk, and reconsideration trigger.

## Workflow

1. **Frame the decision and scope.**
   - Identify what the plan must inform: release confidence, regression coverage, defect verification, component acceptance, or audit evidence.
   - Record the target version, properties, routes, components, roles, locales, states, critical tasks, deadline, and exclusions.
   - Distinguish expert AT testing from keyboard review, automated checks, standards auditing, and research with disabled participants.
   - State that the plan cannot by itself establish WCAG conformance.

2. **Build a risk and evidence profile.**
   - Rank tasks by criticality, frequency, user impact, breadth, workaround quality, irreversibility, and history of failure.
   - Inventory interface patterns that change AT risk: custom widgets, dialogs, validation, live regions, client-side routing, tables, charts, media, drag-and-drop, gestures, canvas, time limits, authentication, and recovery.
   - Record audience and environment evidence separately from assumptions.
   - Identify unique implementations that cannot safely inherit evidence from a shared component or template.

3. **Choose a representative task sample.**
   - Include every critical end-to-end task and unique high-risk interaction.
   - Add representative frequent tasks, shared navigation, authentication, help, cancellation, error recovery, and state changes.
   - Include success plus relevant validation, loading, empty, timeout, permission, session-expiry, offline, and partial-success paths.
   - For components, include every materially different variant, state, composition, input method, and responsive mode.
   - Document what each task represents, what remains untested, and the trigger for expanding the sample.

4. **Select environments proportionately.**
   - Begin with current supported combinations and any combinations explicitly used by the audience.
   - Prefer primary pairings known to work together; do not arbitrarily cross every screen reader with every browser.
   - Add another combination only when it covers a different priority platform, interaction model, browser engine, AT implementation, audience segment, or known risk.
   - Include desktop and mobile screen readers only where the supported product surface or audience justifies both.
   - Include keyboard-only testing for interactive targets.
   - Select zoom or magnification, voice control, switch or alternative input, and high-contrast or forced-colors modes using the coverage model.
   - For every included or excluded modality, record the selection rationale, evidence source, priority, prerequisites, limitations, and residual risk.

5. **Define each test case.**
   Give every case a stable ID and specify:
   - **Objective and risk:** the behavior or user outcome being assessed and why it matters.
   - **Target:** route, component, flow step, state, role, locale, viewport, and occurrence.
   - **Environment:** device, OS, browser, AT or input method, versions, settings, orientation, zoom, display mode, and date.
   - **Starting conditions:** clean or retained session, authentication, focus location, navigation mode, page position, permissions, network state, feature flags, and preloaded data.
   - **Test data:** exact valid, invalid, boundary, duplicate, lengthy, localized, private-safe, and recovery data required; include reset or cleanup notes.
   - **Task:** a user-goal statement followed by reproducible actions. Avoid over-coaching testers with internal control names unless the case is a regression script.
   - **Expected behavior:** observable task outcome plus expected operability, focus, name, role, state, value, reading order, announcement, feedback, error identification, recovery, and persistence where relevant.
   - **Observations to record:** actual output and actions, unexpected verbosity or silence, focus path, command used, blocked or confusing step, workaround, timing, repeated behavior, and user impact.
   - **Evidence:** required notes, screenshots, recordings, speech-viewer or event logs, accessibility-tree extracts, and defect references, with privacy redaction rules.
   - **Result values:** `pass`, `fail`, `blocked`, `not-run`, or `needs-investigation`; never coerce missing evidence into `pass`.

6. **Add modality-specific protocols.**
   - **Desktop screen reader:** cover browse or reading navigation, headings and landmarks, controls, forms, errors, dialogs, tables, dynamic updates, and task completion as applicable.
   - **Mobile screen reader:** cover touch exploration, sequential swipe navigation, activation, gestures, virtual-keyboard entry, orientation, rotor or local navigation features, and responsive state changes as applicable.
   - **Keyboard only:** cover logical sequence, reachability, visible focus, activation, composite-widget keys, escape or cancellation, focus return, traps, shortcuts, and recovery.
   - **Zoom or magnification:** cover selected zoom or magnifier settings, reflow, panning burden, pointer tracking, focus visibility, sticky content, overlays, tooltips, and loss or overlap of information and controls.
   - **Voice control:** cover discovering target names, unique labels, activation, dictation, editing, disambiguation, overlays, custom controls, and completion without touch or pointer fallback.
   - **Switch or alternative input:** cover scanning or keyboard equivalence, group order, dwell or timing constraints, repeated actions, escape, gesture or drag alternatives, target reachability, and recovery.
   - **Forced colors or high contrast:** cover text, icons, boundaries, focus, selected and disabled states, form controls, validation, charts, images, and custom properties that may disappear or become indistinguishable.

7. **Order execution and assign ownership.**
   - Validate access, fixtures, reset paths, capture tools, and one smoke test before the full pass.
   - Run stable baseline tasks before destructive, error, timeout, or recovery cases.
   - Reuse a combination only where doing so answers the same risk; avoid duplicated low-value cases.
   - Assign a tester and reviewer for each work package, noting required product and AT proficiency.
   - Identify cases that may run in parallel and dependencies that must remain stable.
   - Include time for defect reproduction, evidence review, blocked-case resolution, targeted retests, and gap reporting.

8. **Define stopping and expansion criteria.**
   - Stop the planned pass when every in-scope case has an allowed result, required evidence is stored, failures are reproducible or explicitly marked unresolved, blocked and not-run cases have owners or accepted gaps, and coverage has been reviewed against the selection rationale.
   - Stop a single case early for safety, privacy, irreversible production impact, corrupted fixtures, unavailable prerequisites, or an environment mismatch; record the reason and do not mark it passed.
   - Expand the sample when a critical task fails, a shared component behaves inconsistently, failures cluster across targets, a workaround is absent, new audience or support evidence appears, a chosen combination exposes engine-specific behavior, or retained evidence contradicts current results.
   - Pause and repair the environment when a smoke test shows the build, account, data, AT, browser, capture method, or test instructions are unreliable.
   - Do not stop merely because no defect has yet been found or an automated scan passed.

9. **Review limitations and handoff.**
   - List untested combinations, tasks, states, roles, locales, versions, settings, and third-party content.
   - State the claims the evidence supports and the claims it does not.
   - Identify prerequisite gaps, residual risks, proposed follow-up tests, and decisions requiring product or accessibility leadership.
   - When findings will enter a broader audit, reference the orchestrator's shared finding contract instead of creating a competing defect schema.

## Orchestrator alignment

When `inclusive-interface-audit-orchestrator` invokes this skill:

- Preserve its scope identifiers, target inventory, priority, evidence model, allowed finding values, severity language, and explicit exclusions.
- Use its selected tasks and representative sample unless AT-specific evidence justifies expansion; record the trigger rather than silently changing scope.
- Return this plan as an execution work package with combination rationales, prerequisites, cases, evidence requirements, dependencies, and coverage gaps.
- Require executed failures to use the orchestrator's shared finding contract. This planning skill itself returns no audit findings.
- Do not duplicate keyboard, visual-responsive, dynamic-interface, or other specialist work. Cross-reference shared cases and name the distinct AT question each combination answers.

When the orchestrator is unavailable, use the standalone output format below. Do not invent an orchestrator schema.

## Output format

Return:

```md
## Plan summary

- Target and version:
- Decision supported:
- In scope:
- Out of scope:
- Critical tasks:
- Evidence basis:
- Assumptions and open decisions:
- WCAG/conformance limitation:

## Risk-ranked task sample

| Task ID | User goal and states | Risk and priority | Representative of | Expansion trigger |
|---|---|---|---|---|

## Environment selection

| Environment ID | Device / OS | Browser | AT or input mode | Versions and settings | Tasks | Priority | Selection evidence and rationale | Limitations |
|---|---|---|---|---|---|---|---|---|

## Excluded or deferred coverage

| Modality or combination | Decision | Rationale and evidence | Residual risk | Reconsideration trigger |
|---|---|---|---|---|

## Test cases

### [Case ID]: [task and environment]

- Objective and risk:
- Target:
- Starting conditions:
- Test data:
- Task:
- Actions:
- Expected behavior:
- Observations to record:
- Evidence required and location:
- Cleanup or reset:
- Result: pass | fail | blocked | not-run | needs-investigation

## Execution schedule and ownership

| Work package | Cases | Owner / reviewer | Prerequisites | Dependencies | Evidence location | Completion gate |
|---|---|---|---|---|---|---|

## Stopping and expansion criteria

- Planned-pass completion:
- Per-case safety stops:
- Environment pause conditions:
- Sample expansion triggers:

## Coverage gaps and handoff

- Untested scope:
- Blocked prerequisites:
- Residual risks:
- Follow-up decisions:
- What the evidence may support:
- What the evidence cannot establish:
```

## Quality bar

The task is complete only when:

- Exact product names and versions come from supplied support or availability evidence, or are clearly labeled proposals.
- Every selected combination answers a named product, audience, platform, interaction, or risk question.
- Every relevant modality is included or explicitly excluded with rationale and residual risk.
- Critical tasks, high-risk patterns, meaningful states, and recovery paths receive proportionate coverage.
- Each case defines starting conditions, expected behavior, observations, test data, evidence, cleanup, and an allowed result.
- Keyboard-only testing is distinct from screen-reader testing.
- Desktop and mobile screen-reader coverage is selected deliberately rather than assumed or multiplied mechanically.
- Stopping, pause, and sample-expansion criteria are observable.
- Evidence is traceable to the tested environment, target version, task, state, settings, and date.
- Missing access or equipment is reported as a gap, not disguised through an invalid substitute.
- The plan states that AT testing alone does not prove WCAG conformance.
- The output can join an orchestrated audit without a competing finding schema and remains independently executable.

## Edge cases

- **No support matrix:** Propose a minimal provisional matrix from product platforms, audience, risk, and available equipment; require owner confirmation before treating it as policy.
- **Very small budget:** Cover critical tasks with the highest-priority supported keyboard and AT combinations, disclose omissions, and retain expansion triggers.
- **One available AT:** Use it only for questions it can answer. Record the uncovered platform, input, and modality risks rather than generalizing.
- **Component without a full application:** Supply a deterministic harness, surrounding label and instructions, initial focus, all meaningful states, representative composition, and reset control.
- **Authenticated or role-based flow:** Provide private-safe accounts and data for each materially different role; do not infer one role from another.
- **Destructive or consequential task:** Use a safe sandbox or reversible fixture and define an early stop before irreversible submission.
- **Third-party content:** Record ownership and control boundaries while keeping the user-facing task risk visible.
- **Intermittent result:** Repeat enough to capture conditions and frequency, preserve recordings or logs, and mark `needs-investigation` until reproducible or explained.
- **AT proficiency gap:** Assign a qualified tester, training time, or external support. Do not interpret unfamiliar operation as a product failure.
- **Native mobile target:** Use platform-specific accessibility guidance and native AT combinations; do not apply web-only expectations blindly.

## Related skills

- `inclusive-interface-audit-orchestrator`
- `wcag-audit-scope-planner`
- `accessibility-validation-planner`
- `keyboard-focus-accessibility-audit`
- `dynamic-interface-accessibility-audit`
- `visual-responsive-accessibility-audit`
- `inclusive-task-flow-review`
- `cross-framework-audit-synthesis`
