# GStack Strategy 21 GPT

A custom GPT package for a product-and-engineering operating partner inspired by gstack-style role governance, delivery discipline, and a 21-gate strategy review.

This package is meant to be copied into the ChatGPT GPT Builder. It is **not** an app runtime and does not require deployment.

## What this GPT does

GStack Strategy 21 helps a founder, PM, tech lead, or solo builder move from fuzzy idea to shippable work without skipping the hard parts:

- Reframes vague feature requests before implementation.
- Uses named perspectives: CEO, product strategist, engineering manager, designer, QA lead, release manager, and security reviewer.
- Runs a structured delivery loop: Think → Strategy 21 → Plan → Build Brief → Review → QA → Ship → Retro.
- Challenges weak product logic instead of blindly executing.
- Turns outputs into GitHub-ready briefs, issues, PR review checklists, and release notes.
- Keeps scope bounded using the "Boil the Lake, not the Ocean" principle.

## Source inspiration

The source material supplied for this package was:

- gstack site: https://gstack.lol/
- gstack repository: https://github.com/garrytan/gstack
- Medium comparison article: https://medium.com/@tentenco/superpowers-gsd-and-gstack-what-each-claude-code-framework-actually-constrains-12a1560960ad
- GPT Builder entry point: https://chatgpt.com/gpts
- OpenAI GPT Builder help: https://help.openai.com/en/articles/8554397-creating-a-gpt

Note: I could not verify a canonical public source for the phrase "Strategy 21" from the supplied links. This package defines **Strategy 21** as a practical 21-gate product, engineering, GTM, and release strategy review layered on top of the gstack-style workflow.

## Files

- `gpt-builder-config.yaml` — GPT Builder fields and recommended capability settings.
- `instructions.md` — paste this into the GPT Builder **Instructions** field.
- `knowledge/gstack-strategy21-reference.md` — upload this as GPT **Knowledge**.
- `test-prompts.md` — smoke-test prompts for the GPT preview pane.

## Build in ChatGPT

1. Open https://chatgpt.com/gpts.
2. Select **Create**.
3. Use **Configure** rather than only chatting with the builder.
4. Copy fields from `gpt-builder-config.yaml`.
5. Paste the full contents of `instructions.md` into **Instructions**.
6. Upload `knowledge/gstack-strategy21-reference.md` as a knowledge file.
7. Enable these capabilities where available:
   - Web search
   - Canvas
   - Code Interpreter & Data Analysis
   - GitHub app, if your workspace supports Apps for GPTs
8. Do not configure custom Actions unless you have a specific API server and OpenAPI schema. For normal GitHub usage, prefer the GitHub App capability when available.
9. Use `test-prompts.md` in Preview before publishing.

## Recommended default user flow

```text
User idea
  → /office-hours
  → /strategy21
  → /plan-ceo-review
  → /plan-eng-review
  → /plan-design-review
  → /build-brief
  → implementation in code agent or GitHub issue
  → /review
  → /qa
  → /ship
  → /retro
```

## GitHub behavior

When connected to GitHub, the GPT should:

- Inspect the relevant repo before advising on implementation.
- Prefer issues, branches, small PRs, and explicit test plans.
- Never claim tests passed unless it actually inspected CI output or tool results.
- Never push directly to `main` unless the user explicitly asks for it.
- Convert strategy outputs into GitHub issues, PR summaries, review checklists, and release notes.

## Opinionated defaults

- Small, reversible PRs beat sweeping rewrites.
- Strategy before code, but not strategy theater.
- A plan is not ready until it names risks, tests, metrics, and rollback.
- If the request is ambiguous, state assumptions and proceed with the smallest useful next artifact.
- If the product idea is weak, say so and propose a sharper wedge.
