# GStack GPT

Custom GPT build kit for GStack Strategy 21: a product and engineering operating partner that turns vague ideas into scoped, testable, GitHub-ready work.

Repository name: `gstack-gpt`

## Start here

Use the ChatGPT GPT Builder **Configure** form. Do not paste YAML or this README into the Instructions field.

1. Open the GPT editor.
2. Fill the fields from `builder-form.md`.
3. Paste only `instructions.md` into **Instructions**.
4. Upload `knowledge/strategy-21-reference.md` under **Knowledge**.
5. Turn on the recommended capabilities from `builder-form.md`.
6. Test with `test-prompts.md` in Preview.
7. Create or Update the GPT.

## Files

| File | Use |
|---|---|
| `builder-form.md` | Field-by-field GPT Builder values |
| `instructions.md` | Copy this into the GPT **Instructions** field |
| `knowledge/strategy-21-reference.md` | Upload this as GPT **Knowledge** |
| `test-prompts.md` | Preview prompts and expected behaviors |

## What this GPT is for

GStack Strategy 21 helps a founder, PM, or builder convert fuzzy product and engineering ideas into useful work artifacts:

- product bets
- sharper user jobs
- scoped build briefs
- GitHub issue bodies
- PR review checklists
- release gates
- reusable decision notes
- retro follow-ups

It is intentionally biased toward small, reversible, evidence-backed changes. It should challenge vague strategy, narrow ocean-sized work, preserve the language of the product area, and leave behind reusable artifacts that get better after every launch.

## What this repo is not

This is not a documentation starter, an app runtime, or a custom Actions server.

Actions are left off by default. Use the GitHub App capability if your GPT workspace exposes it. Add custom Actions only when you have a real external API and an OpenAPI schema.

## Source links

- GStack: https://gstack.lol/
- GStack repository: https://github.com/garrytan/gstack
- GPT Builder help: https://help.openai.com/en/articles/8554397-creating-and-editing-gpts
- GPT editor entry: https://chatgpt.com/gpts
