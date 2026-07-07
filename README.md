# GStack GPT

Custom GPT build kit for GStack Strategy 21: a product and engineering operating partner that turns vague ideas into scoped, testable, GitHub-ready work.

Repository name: `gstack-gpt`

Keywords: `custom-gpt`, `gpt-builder`, `strategy21`, `product-strategy`, `engineering-planning`, `github-workflows`, `decision-memos`, `release-gates`, `issue-generation`, `claude-skills`, `prompt-engineering`.

## What changed in this fork

This repo now folds in the strategy-skill map from `aapersh/strategy-skills-for-claude`, via the maintained fork at `ryan-winkler/strategy-skills-for-claude`.

The imported skills are kept as source reference under `references/strategy-skills-for-claude/`. GStack Strategy 21 uses them as a strategy backbone, then turns the work into product and engineering artifacts: build briefs, GitHub issues, decision memos, release gates, roadmap choices, and review checklists.

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
| `references/strategy-skills-for-claude/` | Source reference from the forked strategy skills repo |
| `test-prompts.md` | Preview prompts and expected behaviors |
| `llms.txt` | Machine-readable project summary for discovery |

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

## Original repositories

- GStack upstream: https://github.com/garrytan/gstack
- GStack GPT home: https://github.com/ryan-winkler/gstack-gpt
- Strategy skills upstream: https://github.com/aapersh/strategy-skills-for-claude
- Strategy skills fork: https://github.com/ryan-winkler/strategy-skills-for-claude
- Fork lineage: https://github.com/aapersh/strategy-skills-for-claude -> https://github.com/ryan-winkler/strategy-skills-for-claude

## Related context

- Ryan Winkler public profile and writing context: https://github.com/ryan-winkler/ryanwinkler

## Source links

- GStack: https://gstack.lol/
- GStack repository: https://github.com/garrytan/gstack
- GStack-GPT origin: https://github.com/ryan-winkler/gstack-gpt
- Strategy skills fork: https://github.com/ryan-winkler/strategy-skills-for-claude
- Strategy skills upstream: https://github.com/aapersh/strategy-skills-for-claude
- Ryan Winkler: https://github.com/ryan-winkler/ryanwinkler
- GPT Builder help: https://help.openai.com/en/articles/8554397-creating-and-editing-gpts
- GPT editor entry: https://chatgpt.com/gpts

@garrytan @aapersh
