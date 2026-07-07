# GStack Strategy 21 Reference

This file is reference material for the GStack Strategy 21 GPT. Behavioral rules belong in `instructions.md`.

## Concept

GStack Strategy 21 combines a gstack-inspired role workflow with a 21-gate strategy rubric.

The operating idea: AI-assisted builders do not usually fail because the model cannot write code. They fail because the work skips product framing, architecture review, QA, release discipline, and learning loops.

## Gstack-inspired delivery loop

1. **Think** — reframe the problem before planning.
2. **Strategy 21** — pressure-test the bet.
3. **Plan** — review through CEO, engineering, design, QA, security, and release perspectives.
4. **Build Brief** — produce a scoped, testable implementation plan.
5. **Review** — inspect the result for regressions, missing tests, scope drift, and hidden risk.
6. **QA** — validate real user journeys or produce a concrete QA plan.
7. **Ship** — confirm tests, docs, rollout, rollback, and comms.
8. **Retro** — capture patterns and improve the next sprint.

## Role lenses

### CEO lens

Focus: customer pain, market timing, opportunity cost, wedge, ambition, sequencing.

Good CEO questions:

- What user problem is this actually solving?
- Is this a must-have or a nice-to-have?
- Why now?
- What makes this wedge sharper than the obvious version?
- What should be cut to make the first version undeniable?

### Product strategist lens

Focus: target user, job-to-be-done, positioning, metric, adoption path.

Good product questions:

- Who is the narrowest user who will care immediately?
- What is the before/after state?
- What behavior proves value?
- What is the smallest version that teaches us something?

### Engineering manager lens

Focus: scope, architecture, data model, dependencies, tests, failure modes, maintainability.

Good engineering questions:

- What existing system boundary does this touch?
- What can break?
- What data changes are required?
- How do we test this without relying on happy-path demos?
- Is rollback possible?

### Designer lens

Focus: user flow, comprehension, states, accessibility, information hierarchy, AI slop.

Good design questions:

- What is the primary user path?
- What happens when there is no data?
- What happens on slow load, error, permission failure, or partial success?
- Is the copy specific or generic?
- Is the UI doing too much?

### QA lead lens

Focus: user journey validation, regression coverage, edge cases, fixtures, smoke tests.

Good QA questions:

- What is the critical path?
- What is the highest-risk edge case?
- What regression test would catch this bug next time?
- What would make this unsafe to ship?

### Security reviewer lens

Focus: auth, authorization, privacy, injection, secrets, auditability, abuse cases.

Good security questions:

- Does this expose private data?
- Are permissions checked server-side?
- Can user input alter execution or queries?
- Are secrets or tokens handled safely?
- Is logging safe and useful?

### Release manager lens

Focus: release readiness, flags, rollout, monitoring, rollback, comms, docs.

Good release questions:

- What proves this is ready to ship?
- Can it be rolled out gradually?
- What metric or alert catches failure early?
- How do we revert?
- What must support/docs know?

## Strategy 21 gates

Score each gate as:

- **Green** — strong enough to proceed.
- **Yellow** — acceptable but needs sharpening.
- **Red** — blocks shipping or requires scope change/research.

### 1. User pain

Is the pain real, specific, and costly enough that the user will change behavior?

Red flags: generic productivity claims, no named user, no clear pain frequency.

### 2. Target user

Is the initial user segment narrow enough to design for?

Red flags: "everyone", "teams", "SMBs", "developers" without a sharper persona.

### 3. Job to be done

Can the user job be stated as a concrete before/after transformation?

Template: "When [situation], I want to [action], so I can [outcome]."

### 4. Must-win moment

Is there a single moment in the experience where the product must feel obviously valuable?

Red flags: value only appears after long setup or many weak steps.

### 5. Urgency

Why does this need to exist now rather than later?

Look for deadlines, budget pressure, regulatory change, workflow pain, market shift, or repeated failure.

### 6. Market timing

Is there a timing advantage?

Examples: new platform capability, cost collapse, behavior shift, regulation, distribution channel opening.

### 7. Unique wedge

What makes this version sharper than the obvious clone?

A wedge can be workflow, data, audience, distribution, insight, speed, integration, or trust.

### 8. Anti-goal

What will this first version intentionally not do?

A strong anti-goal protects the lake from becoming an ocean.

### 9. Success metric

What measurable behavior proves the bet worked?

Prefer product behavior over vanity metrics.

Examples: activation rate, repeat use, completed workflow, time saved, error reduction, revenue conversion.

### 10. Failure metric

What measurable signal tells us to stop, narrow, or rethink?

Examples: low activation, support spike, poor retention, high latency, high failure rate, no qualitative pull.

### 11. One-sprint deliverable

Can a useful version ship in one sprint?

If not, narrow until it can.

### 12. Lake vs ocean

Is the scope bounded and measurable?

Lake: one workflow, one module, one user, one metric.

Ocean: full platform rewrite, broad automation, universal dashboard, vague AI assistant.

### 13. Data model

Are the core entities, states, and ownership rules clear?

Red flags: unclear source of truth, hidden migration, ambiguous permissions.

### 14. Failure modes

Are likely failures named before build?

Include product, technical, UX, security, data, and operational failures.

### 15. Test plan

Are tests explicit and tied to acceptance criteria?

Include unit, integration, E2E, regression, and smoke tests where relevant.

### 16. UX acceptance

Are user states and quality criteria explicit?

Include empty, loading, success, error, permission, and partial-success states.

### 17. Security and privacy

Are auth, authorization, data exposure, logging, secrets, and abuse cases covered?

Red blocks include credential leakage, missing server-side authz, unbounded data export, and unsafe user input handling.

### 18. Rollout and rollback

Can the change be shipped safely and reversed?

Look for flags, staged rollout, migration rollback, data backfill plan, and monitoring.

### 19. Docs and support

Does the release require user docs, internal docs, support macros, onboarding, or migration notes?

### 20. Telemetry and learning loop

Will the team know whether the release worked?

Include analytics events, dashboards, logs, alerts, qualitative feedback, and retro questions.

### 21. Next decision threshold

What exact evidence triggers the next decision?

Examples:

- Ship wider if 30% of invited users complete setup within 24 hours.
- Narrow if activation is below 10% after 20 users.
- Kill if no user repeats the workflow twice in a week.

## Verdict guide

### Ship

Use when the bet is scoped, measurable, testable, and reversible.

### Narrow

Use when the core idea is good but the current scope is too broad or risky.

### Research

Use when the main blocker is missing evidence rather than weak strategy.

### Kill

Use when the pain, user, wedge, or metric is too weak to justify building.

## Standard artifacts

### GitHub issue template

```markdown
## Summary

## Problem

## Target user

## Goals

## Non-goals

## Scope

## Acceptance criteria

- [ ]

## Technical notes

## Test plan

- [ ]

## Rollout

## Rollback

## Open questions
```

### PR description template

```markdown
## Summary

## Changes

## Tests

## Risk

## Rollout / rollback

## Screenshots or recordings

## Follow-ups
```

### Release gate template

```markdown
## Ship decision

Ship / Hold

## Required checks

- [ ] Tests pass
- [ ] Critical user journey checked
- [ ] Error states checked
- [ ] Docs/support updated
- [ ] Monitoring in place
- [ ] Rollback path exists

## Release notes

## Owner

## Backout plan
```

## Common anti-patterns

- Starting with implementation before the target user and metric are clear.
- Treating "AI assistant" as the product instead of a workflow-specific wedge.
- Shipping a demo path with no error, empty, loading, permission, or rollback states.
- Saying "we will measure engagement" without naming the event and threshold.
- Writing a plan that cannot become a GitHub issue.
- Calling a rewrite a sprint.
- Trusting model-generated code without review, tests, QA, and release gates.
