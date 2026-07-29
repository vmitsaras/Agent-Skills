---
name: accessibility-regression-test-planner
description: Converts confirmed accessibility findings, completed remediations, and stable critical-interaction contracts into a risk-based regression test plan spanning unit tests, component tests, browser automation, axe integrations, keyboard checks, visual regression, manual release checks, and assistive-technology smoke tests. Use after audits are producing stable findings or when a team needs to decide which accessibility regressions to automate, which checks must remain manual, where each check belongs, and which low-value test ideas should be rejected.
license: MIT
compatibility: Portable Agent Skill. Can be copied into an Agent Skills-compatible environment with repository or test-artifact access. Reliable layer selection benefits from access to existing tests and tooling; assistive-technology coverage requires representative runtime environments.
metadata:
  category: frontend-a11y
  task_type: planner
  audience: accessibility-engineers-frontend-developers-and-qa-teams
  tags:
    - accessibility
    - regression-testing
    - test-strategy
    - automated-testing
    - axe
    - keyboard
    - visual-regression
    - assistive-technology
  status: draft
  side_effects: none
---

# Accessibility Regression Test Planner

## Purpose

Turn stable, evidence-backed accessibility findings and critical interaction contracts into a small, durable regression portfolio. Select the narrowest reliable test layer, retain human or assistive-technology judgment where automation cannot establish the outcome, and reject tests that add maintenance cost without protecting a meaningful user-facing behavior.

This skill produces a plan. It does not perform an audit, implement tests, certify conformance, or treat test count as a quality goal.

## When to use this skill

Use this skill when:

- An accessibility audit has confirmed repeatable findings with evidence, impact, and retest expectations.
- A remediation needs regression coverage before the finding can be closed.
- A stable keyboard, focus, semantic, announcement, reflow, contrast, motion, or error-recovery contract must be preserved.
- A critical interaction has no prior defect but its accessibility behavior is important enough to protect proactively.
- A team needs to choose among unit, component, browser, axe, keyboard, visual, manual, and assistive-technology checks.
- Existing accessibility tests are duplicated, brittle, too broad, or disconnected from findings and user risk.

Do not use this skill when:

- Findings are still provisional, unreproduced, or waiting for evidence; validate them before planning regression coverage.
- The task is to define broad accessibility validation before an audit or without stable findings; use `accessibility-validation-planner`.
- The user wants the audit itself, test implementation, or test execution rather than a plan.
- The only objective is to raise a coverage percentage or create one test per WCAG criterion.
- The user requests legal advice, certification, or a complete conformance determination.

## Inputs to inspect

Start with the smallest relevant evidence set:

- Confirmed finding records, including stable IDs, status, target, environment, evidence, user impact, root cause, recommendation, and retest procedure.
- Closure or remediation evidence when a fix already exists.
- Critical user tasks and interaction contracts, including expected keyboard, focus, semantic, status, error, and assistive-technology behavior.
- Affected components, routes, variants, states, breakpoints, themes, locales, and shared primitives.
- Existing unit, component, integration, browser, visual, accessibility, and manual test suites.
- Test configuration, fixtures, stories, selectors, helpers, axe integrations, CI workflows, and supported browser or assistive-technology matrix.
- Regression history, escaped defects, release cadence, flakiness constraints, runtime budgets, ownership, and manual release procedures.

If a finding lacks a stable expected outcome or reproducible target, move it to a validation backlog instead of inventing a regression test.

## Regression planning rules

- Protect a user-observable accessibility contract, not the implementation detail used by the current fix.
- Prefer the narrowest layer that can reliably observe the failure. Escalate only when the behavior crosses rendering, routing, focus, timing, browser, or integration boundaries.
- Treat test layer and test method separately. For example, axe may run in a component or browser test, and keyboard behavior may be exercised in a component test, browser test, or manual procedure.
- Group manifestations that share one root cause or invariant, while preserving traceability to every affected finding, path, and variant.
- Add defense in depth only when two checks detect materially different failure modes or protect different boundaries.
- Use representative coverage with explicit expansion triggers when exhaustive combinations would be costly or redundant.
- Do not call a check automated merely because a tool can produce output. Automation must provide a deterministic, interpretable failure signal.
- Do not call a check inherently manual merely because the current harness is missing. Mark it `automate-after-enabler` when the behavior is automatable after a proportionate fixture, hook, or environment improvement.
- Make every recurring manual check as repeatable as an automated one: define setup, actions, expected result, environment, evidence, cadence, and owner role.
- Prioritize by user impact, task criticality, recurrence risk, affected breadth, and detectability—not by ease of writing a test or coverage metrics.

## Test-layer guide

| Surface or method | Strong fit | Do not use as sole evidence for |
|---|---|---|
| Unit test | Pure state transitions, attribute helpers, message selection, deterministic focus-target selection, and other logic without browser behavior | Rendered semantics, computed names, layout, real focus movement, or assistive-technology output |
| Component test | Rendered role, name, state, relationships, local keyboard behavior, focus changes, errors, and stable component variants | Cross-route behavior, browser integration, layout-dependent behavior, or full task completion |
| Browser automation | Critical flows, tab order, focus containment or restoration, async updates, portals, navigation, browser defaults, and integration across components | Human judgment, actual spoken output, meaning, usability, or every browser and assistive-technology combination |
| Axe integration | Rule-detectable issues in stable component states or representative pages, preferably scoped near the regression | Keyboard operation, focus logic, announcement quality, reading experience, task completion, or full conformance |
| Keyboard check | Key sequence, reachability, activation, navigation, Escape behavior, focus destination, and focus return at component or browser level | Whether a pattern is understandable, efficient, or announced usefully without complementary human checks |
| Visual regression | Stable focus styling, clipping, overlap, reflow, forced-colors states, hidden content, or other deterministic visual contracts | Semantic exposure, keyboard operation, accessible names, actual contrast measurement, or behavior hidden by noisy snapshots |
| Manual release check | Meaning, clarity, discoverability, unusual platform behavior, high-judgment interactions, and critical flows not reliably automated | Vague instructions such as “check accessibility” or routine deterministic checks that reliable automation can cover |
| Assistive-technology smoke test | Representative role, name, state, context, reading order, navigation, announcements, and critical task completion in supported combinations | Exact phrasing across tools, exhaustive compatibility, or behavior that a lower layer can protect more cheaply and reliably |

## Candidate dispositions

Assign every candidate one disposition:

- `covered-existing`: An existing reliable check already protects the contract; link it and add no duplicate.
- `automate-now`: The behavior is stable, observable, deterministic, and worth its maintenance cost.
- `automate-after-enabler`: Automation is valuable, but a named fixture, hook, selector, environment, or harness change is required first.
- `manual-recurring`: Human or assistive-technology judgment is essential, or reliable automation is not proportionate. Define a recurring procedure and cadence.
- `do-not-add`: The candidate is redundant, implementation-coupled, low-signal, unstable, or unrelated to meaningful regression risk. Record the reason.

A single source finding may justify complementary automated and manual checks. Give each check its own row and explain the distinct failure signal.

## Workflow

1. **Confirm source readiness.**
   - Admit confirmed findings, remediated findings with closure evidence, and explicitly documented critical-interaction contracts.
   - Keep provisional findings, `needs-validation` items, coverage gaps, and unverified assumptions outside the regression plan.
   - Allow an unresolved confirmed finding only when the intended corrected behavior is agreed; mark its check as blocked until the fix exists.

2. **Normalize each regression source.**
   - Record the source ID, target, trigger, environment, user impact, root cause, affected breadth, corrected invariant, and canonical retest.
   - Label the source as `confirmed-finding`, `escaped-regression`, or `preventive-critical-interaction`.
   - Preserve original finding IDs even when several findings are merged into one test contract.

3. **Identify meaningful contracts.**
   - Restate each candidate as setup, action, and observable expected result.
   - Assert what a user can perceive or operate: role, name, state, relationship, focus location, keyboard result, status, reading order, layout, preference response, recovery, or task completion.
   - Reject candidates with no stable expected result or plausible failure signal.

4. **Group by root cause and boundary.**
   - Merge duplicate symptoms when one invariant and one test can protect them.
   - Split candidates when they need different environments, fixtures, owners, cadences, or failure diagnostics.
   - Retain the affected path and variant list even when a representative sample is chosen.

5. **Assess regression risk and value.**
   - Consider severity of user impact, criticality of the task, likelihood of recurrence, reuse of the affected primitive, history of regressions, and likelihood that ordinary review would miss the failure.
   - Identify the smallest check that would have caught the original defect before release.
   - Drop ceremonial tests whose likely signal does not justify their runtime, flakiness, or maintenance burden.

6. **Select the layer and method.**
   - Start at unit or component level and escalate to browser automation only when the contract crosses a lower-layer boundary.
   - Add axe where a rule reliably detects the relevant condition; scope it to the state that matters and name its blind spots.
   - Apply keyboard or visual methods at the layer that can observe the contract.
   - Reserve manual and assistive-technology checks for outcomes requiring actual platform behavior or human judgment.

7. **Decide automation feasibility.**
   - Choose a candidate disposition using observability, determinism, harness availability, diagnostic quality, execution cost, flakiness risk, and maintenance cost.
   - Name any automation enabler and decide whether its cost is proportionate to the protected risk.
   - Do not replace a required manual outcome with an accessibility-tree snapshot, DOM assertion, or axe result that proves something weaker.

8. **Design stable test cases.**
   - Specify minimal fixtures, data, state, viewport, preferences, theme, locale, and environment.
   - Use resilient queries based on user-facing roles, names, or stable test contracts rather than incidental markup, CSS classes, timing, or serialized DOM.
   - Define the assertion, diagnostic evidence, and cleanup.
   - When feasible, require proof that the check fails against the known-broken behavior and passes after remediation; otherwise specify a targeted mutation or equivalent false-positive challenge.

9. **Plan representative variants.**
   - Cover the canonical failure condition and the smallest meaningful set of shared primitives, states, or environments.
   - Define expansion triggers such as a new input mode, changed interaction model, repeated escape, browser-specific failure, or divergence among variants.
   - Avoid multiplying identical checks across pages when one shared component test plus one representative integration test protects the same contract.

10. **Plan manual and assistive-technology coverage.**
    - Define exact steps, expected equivalent outcome, evidence to record, browser and assistive-technology combination, cadence, and owner role.
    - Use a risk-based smoke matrix rather than claiming exhaustive compatibility.
    - Avoid exact speech-string assertions unless exact wording is itself a product requirement and stable across the supported environment.

11. **Deduplicate and sequence the portfolio.**
    - Link existing checks before proposing new ones.
    - Sequence shared enablers first, then high-risk automated checks, complementary manual checks, and lower-priority follow-up.
    - Assign execution triggers such as pull request, component CI, route smoke suite, nightly run, release candidate, or post-dependency-upgrade.
    - Identify findings or critical interactions that remain unprotected and state the residual risk.

12. **Define ownership and maintenance.**
    - Assign an owner role for each recurring check.
    - Define flake triage, fixture review, environment updates, and retirement criteria.
    - Retire or replace a check only when its source contract is removed, superseded, or protected more reliably elsewhere; preserve the traceability record.

13. **Review the plan for signal.**
    - Confirm that every proposed check protects a named source and could fail for the intended regression.
    - Remove duplicate, vague, snapshot-only, implementation-coupled, or coverage-driven tests.
    - Confirm that manual and assistive-technology work is explicit rather than hidden behind an “automation complete” claim.

## Output format

Return the plan using this structure:

```md
## Scope and readiness

- Findings or interactions considered: ...
- Ready for regression planning: ...
- Returned to validation: ...
- Assumptions and supported environments: ...

## Source-to-coverage map

| Source IDs | Target and protected contract | Risk | Automated coverage | Manual or AT coverage | Disposition | Rationale |
|---|---|---|---|---|---|---|

## Automated check plan

| Test ID | Source IDs | Layer | Method | Setup, action, and assertion | Proposed suite or file | Trigger | Stability guard |
|---|---|---|---|---|---|---|---|

## Manual and assistive-technology plan

| Check ID | Source IDs | Method and environment | Procedure | Expected result | Evidence | Cadence | Owner role |
|---|---|---|---|---|---|---|---|

## Enablers, exclusions, and gaps

| Candidate or source | Disposition | Blocker or rationale | Next trigger or residual risk |
|---|---|---|---|

## Implementation sequence

1. ...

## Maintenance and release gates

- Pull-request gates: ...
- Release checks: ...
- Flake and failure triage: ...
- Expansion and retirement triggers: ...
```

For a small remediation, keep the output concise and omit empty sections. Never omit the source-to-coverage decision or the reason a candidate remains manual, is deferred, or is rejected.

## Quality bar

The task is complete only when:

- Every admitted source is confirmed or is an explicitly documented critical-interaction contract.
- Every proposed check traces to source IDs and a user-observable accessibility outcome.
- The plan distinguishes test layer, test method, and automation disposition.
- The narrowest reliable layer is chosen and cross-layer duplication has a stated reason.
- Automated checks have deterministic assertions, meaningful failure signals, and proportionate stability guards.
- Manual and assistive-technology checks have repeatable procedures, environments, evidence, cadence, and ownership.
- Axe, accessibility-tree, DOM, keyboard, visual, and assistive-technology evidence are not treated as interchangeable.
- Known-broken behavior or an equivalent challenge can demonstrate that high-priority automated checks are capable of failing.
- Low-value and coverage-driven candidates are explicitly rejected rather than silently added.
- Unprotected critical interactions, missing enablers, assumptions, and residual risks remain visible.
- The result remains a plan and does not modify tests unless the user separately asks for implementation.

## Edge cases

- **Finding fixed before a test exists:** Use closure evidence to reconstruct the broken and corrected contract; require a targeted mutation or archived failing fixture when replaying the old version is impractical.
- **Confirmed but unresolved finding:** Plan the check, mark implementation blocked on remediation, and do not encode the inaccessible behavior as the expected result.
- **Accepted risk:** Do not create a passing test that normalizes the barrier. Record the decision, monitoring or manual obligations, review date, and trigger for reconsideration.
- **Third-party component:** Protect the integration boundary the team controls, pin or record the tested version, and keep unsupported internals out of the test contract.
- **Shared primitive with many consumers:** Test the invariant at the primitive, add representative consumer integration coverage, and define when the sample must expand.
- **Browser or assistive-technology disagreement:** Preserve the product-level equivalent outcome, document environment-specific expectations, and avoid assuming one exact output is universal.
- **Flaky timing or animation:** Control clocks, transitions, data, and asynchronous completion where possible; otherwise retain a bounded manual check until reliable observability exists.
- **Visual instability:** Crop to the meaningful region, fix the state and viewport, and prefer semantic or computed assertions when pixels are incidental.
- **No existing harness:** Recommend the minimum enabler for high-value automation and keep the immediate recurring manual procedure explicit.
- **No candidates survive the value filter:** Return an empty automated plan with reasons. Do not invent tests merely to make the plan look complete.

## Related skills

- `accessibility-validation-planner`
- `cross-framework-audit-synthesis`
- `edge-case-test-planner`
- `implementation-checkpoint-planner`
