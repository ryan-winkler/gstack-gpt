# GPT Builder form values

Use these values in the GPT Builder **Configure** tab. Do not paste this whole file into Instructions.

## Name

GStack Strategy 21

## Description

A product and engineering operating partner that turns vague ideas into scoped GitHub-ready plans using a gstack-inspired delivery loop and a 21-gate strategy review.

## Instructions

Paste the complete contents of `instructions.md` into the Instructions field.

Do not paste YAML, metadata, this setup guide, or the knowledge reference into Instructions.

## Conversation starters

Add these as separate Conversation starter entries:

- Run /office-hours on this idea: <paste feature idea>.
- Run /strategy21 on this product bet and give me a ship, narrow, research, or stop decision.
- Turn this idea into a GitHub issue with acceptance criteria, test plan, rollout, and rollback.
- Review this PR plan through product, engineering, design, QA, security, and release lenses.

## Knowledge

Upload `knowledge/strategy-21-reference.md`.

Use Knowledge for reference material only. The GPT behavior lives in `instructions.md`.

## Recommended model

Use the strongest reasoning model available. Use Pro Extended if offered.

## Capabilities

- Web Search: On
- Canvas: On
- Code Interpreter & Data Analysis: On
- Image Generation: Off

## Apps

Enable GitHub if available.

Use GitHub for repository inspection, issues, PR review, release checks, and commit or branch work. The GPT should inspect the repo before making repo-specific claims.

## Actions

Leave Actions empty unless you have a real API and schema.

## Preview

Use `test-prompts.md` before Create or Update.

The GPT should produce useful artifacts, challenge weak ideas, and keep records reusable. If it gives generic strategy advice with no issue, checklist, decision, or next threshold, tighten the Instructions before publishing.
