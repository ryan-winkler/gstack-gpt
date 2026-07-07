# Strategy 21 Reference

This file is uploaded as GPT Knowledge. It provides reference material the GPT can draw from during conversations. Behavioral rules belong in `instructions.md`.

## Concept

GStack Strategy 21 combines a gstack-style delivery loop with a 21-gate strategy review.

The common failure mode in AI-assisted building is not that the model cannot produce code. The common failure is skipping product framing, bounded scope, architecture review, QA, release discipline, and the learning loop.

## Delivery loop

1. Think — reframe the problem before planning.
2. Strategy 21 — pressure-test the bet.
3. Plan — review through product, engineering, design, QA, security, and release lenses.
4. Build Brief — produce scoped, testable implementation work.
5. Review — inspect the result for regressions, missing tests, scope drift, and hidden risk.
6. QA — validate real user journeys or produce a concrete QA plan.
7. Ship — confirm tests, docs, rollout, rollback, and comms.
8. Retro — capture what changed and improve the next sprint.

## Product language

Use these terms consistently.

| Term | Meaning |
|---|---|
| Product bet | A proposed change plus the reason it should matter |
| Target user | The narrow first user whose pain drives the work |
| User job | The before/after transformation the product enables |
| Wedge | The sharp reason this version can win where generic versions do not |
| Anti-goal | What the first version deliberately avoids |
| Decision threshold | The evidence that decides ship, narrow, research, or stop |
| Work item | A concrete artifact such as an issue, PR, checklist, or release note |
| Learning note | A reusable record of what changed and how future work should improve |

## Role lenses

### CEO lens

Focus on customer pain, timing, opportunity cost, wedge, ambition, and sequence.

Good questions:

- What user problem is this actually solving?
- Is this a must-have or a nice-to-have?
- Why now?
- What makes this sharper than the obvious version?
- What should be cut to make the first version undeniable?

### Product strategist lens

Focus on target user, job, positioning, metric, adoption path, and learning loop.

Good questions:

- Who is the narrowest user who will care immediately?
- What is the before/after state?
- What behavior proves value?
- What is the smallest version that teaches us something?

### Engineering manager lens

Focus on scope, architecture, data model, dependencies, tests, failure modes, and maintainability.

Good questions:

- What system boundary does this touch?
- What entities, states, and ownership rules matter?
- What can break?
- What data changes are required?
- How do we test this beyond the happy path?
- Is rollback possible?

### Designer lens

Focus on user flow, comprehension, states, accessibility, information hierarchy, and copy quality.

Good questions:

- What is the primary user path?
- What happens when there is no data?
- What happens on slow load, error, permission failure, or partial success?
- Is the copy specific or generic?
- Is the UI doing too much?

### QA lead lens

Focus on critical journeys, regression coverage, edge cases, fixtures, and smoke tests.

Good questions:

- What is the critical path?
- What is the highest-risk edge case?
- What test would catch this bug next time?
- What would make this unsafe to ship?

### Security reviewer lens

Focus on authentication, authorization, privacy, injection, secrets, auditability, and abuse cases.

Good questions:

- Does this expose private data?
- Are permissions checked server-side?
- Can user input alter execution or queries?
- Are secrets handled safely?
- Is logging safe and useful?

### Release manager lens

Focus on readiness, flags, rollout, monitoring, rollback, comms, and docs.

Good questions:

- What proves this is ready to ship?
- Can it be rolled out gradually?
- What metric or alert catches failure early?
- How do we revert?
- What must support or docs know?

## Strategy 21 gates

Score each gate as Green, Yellow, or Red.

### 1. User pain

Is the pain real, specific, and costly enough to change behavior?

### 2. Target user

Is the initial user segment narrow enough to design for?

### 3. User job

Can the job be stated as a concrete before/after transformation?

Template: When [situation], I want to [action], so I can [outcome].

### 4. Must-win moment

Is there a single moment where the product must feel obviously valuable?

### 5. Urgency

Why does this need to exist now rather than later?

### 6. Market timing

Is there a timing advantage from platform shifts, cost changes, behavior shifts, regulation, or distribution changes?

### 7. Unique wedge

What makes this version sharper than the obvious clone?

### 8. Anti-goal

What will this first version intentionally not do?

### 9. Success metric

What measurable behavior proves the bet worked?

### 10. Failure metric

What measurable signal tells us to stop, narrow, or rethink?

### 11. One-sprint deliverable

Can a useful version ship in one sprint?

### 12. Lake vs ocean

Is the scope bounded and measurable?

Lake: one workflow, one module, one user, one metric.

Ocean: full platform rewrite, broad automation, universal dashboard, vague AI assistant.

### 13. Data model

Are the core entities, states, and ownership rules clear?

### 14. Failure modes

Are likely product, technical, UX, security, data, and operational failures named before build?

### 15. Test plan

Are tests explicit and tied to acceptance criteria?

### 16. UX acceptance

Are empty, loading, success, error, permission, and partial-success states covered?

### 17. Security and privacy

Are auth, authorization, data exposure, logging, secrets, and abuse cases covered?

### 18. Rollout and rollback

Can the change be shipped safely and reversed?

### 19. Docs and support

Does the release require user docs, internal docs, support notes, onboarding, or migration notes?

### 20. Telemetry and learning loop

Will the team know whether the release worked?

### 21. Next decision threshold

What exact evidence triggers the next decision?

Examples:

- Ship wider if 30% of invited users complete setup within 24 hours.
- Narrow if activation is below 10% after 20 users.
- Stop if no user repeats the workflow twice in a week.

## Standard artifacts

### GitHub issue body

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

### PR description

```markdown
## Summary

## Changes

## Tests

## Risk

## Rollout / rollback

## Screenshots or recordings

## Follow-ups
```

### Reusable decision note

```markdown
## Context

## Decision

## Evidence

## Scope

## How to verify

## When to revisit
```

### Release gate

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

- Starting implementation before the target user and metric are clear.
- Treating AI assistant as the product instead of a workflow-specific wedge.
- Shipping a demo path with no error, empty, loading, permission, or rollback states.
- Saying engagement will be measured without naming the event and threshold.
- Writing a plan that cannot become a GitHub issue.
- Calling a rewrite a sprint.
- Trusting generated code without review, tests, QA, and release gates.
