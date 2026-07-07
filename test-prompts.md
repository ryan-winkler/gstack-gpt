# Preview smoke tests

Use these in the GPT Builder Preview pane before Create or Update.

## 1. Office-hours reframing

```text
/office-hours I want to build an AI dashboard for founders that summarizes everything in their company.
```

Expected behavior:

- Does not blindly validate the broad dashboard idea.
- Narrows the target user and wedge.
- Produces the smallest useful version.
- Names a clear next artifact.

## 2. Strategy 21 pressure test

```text
/strategy21 We are building a GitHub-connected AI reviewer for solo founders. It reviews PRs for product risk, not just code risk.
```

Expected behavior:

- Produces a Ship / Narrow / Research / Stop verdict.
- Scores all 21 gates.
- Calls out target user, wedge, metric, tests, rollout, and next decision threshold.

## 3. Engineering planning

```text
/plan-eng-review We need to add GitHub issue creation from a product brief. The app already has OAuth, a Postgres database, and a Next.js frontend.
```

Expected behavior:

- Names system boundaries, entities, states, data flow, edge cases, dependencies, test plan, and rollback notes.
- Does not invent repo-specific files unless a repo is connected and inspected.

## 4. Design review

```text
/plan-design-review The user pastes a vague idea, clicks Generate Plan, and gets a GitHub issue draft.
```

Expected behavior:

- Reviews primary flow plus empty, loading, error, permission, and success states.
- Adds copy and accessibility acceptance criteria.

## 5. GitHub issue artifact

```text
/build-brief Turn this into a GitHub issue: founders need a way to pressure-test AI-generated feature ideas before creating implementation tickets.
```

Expected behavior:

- Outputs a complete GitHub issue body.
- Includes goals, non-goals, acceptance criteria, test plan, rollout, rollback, and open questions.

## 6. PR review

```text
/review Here is my PR summary: added a new AI endpoint that accepts arbitrary repo URLs and creates issues automatically. No auth changes. No tests yet.
```

Expected behavior:

- Blocks or requests changes.
- Flags authorization, repository access, abuse, missing tests, logging, and auditability.
- Provides a concrete patch plan.

## 7. Ship gate

```text
/ship We added the GitHub issue generation flow. Unit tests pass, but we have not run browser QA or added rollback docs.
```

Expected behavior:

- Holds the release or narrows ship scope.
- Names blockers and required checks.
- Produces release notes only if safe.

## 8. Retro

```text
/retro We shipped the AI issue generator. It took twice as long because auth edge cases were missed. Users like the issue quality but do not trust auto-create.
```

Expected behavior:

- Extracts lessons.
- Updates the QA and release loop.
- Recommends a narrower next sprint, likely review-before-create.
