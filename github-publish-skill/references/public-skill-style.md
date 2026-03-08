# Public Skill Style Blueprint

Use this style for polished public OpenClaw skill repositories only.

## Hard boundary

Apply this blueprint only when the repo is primarily a skill repo.

Good fit:

- the repo's main artifact is an OpenClaw skill
- the repo contains `<skill-name>/SKILL.md`
- the repo ships `dist/<skill-name>.skill`

Not a fit:

- general software projects
- libraries
- apps
- mixed repos where the skill is only a small side artifact

## Header pattern

```md
# Skill Name

English | [简体中文](README.zh-CN.md)

![Banner](assets/social-preview.svg)

![OpenClaw Skill](...)
![Focus-...](...)
![Works-Standalone](...)
![Artifact-.skill Included](...)
![License-MIT](...)
```

Optional:

- bilingual badge for multilingual repos

## Required narrative sections

- `Quick pitch`
- `Why this exists`
- `Works independently`
- skill-specific behavior section
- `When to use it`
- concrete examples
- `Related skills`
- `Social preview`
- `What you get`
- `Install`
- `Repository layout`
- `Contributing`
- `Release hygiene`
- `Repository`

## Related-skills wording

Use wording like:

- "These are related, not required"
- "Use this repo alone if you only need this lane"
- "Use the umbrella repo when you want the whole operating model"

## Social preview wording

```md
## Social preview

Suggested social preview asset: `assets/social-preview.svg`

Suggested one-line copy:

> ...

GitHub note:

- The current `gh` CLI and GraphQL `UpdateRepositoryInput` do not expose a writable custom social preview field.
- To use this image as the repository social preview, upload `assets/social-preview.svg` manually in the repo settings UI.
```

## CONTRIBUTING shape

Keep it short. Use these sections:

- title
- `Scope`
- `Workflow`
- `Pull request guidance`
- `Repo principle`

## Banner art guidance

Prefer organic shapes, flowing curves, or scene-like forms over generic stacked rectangles and dashboard-looking blocks.

Aim for:

- a clear mood
- a strong text area
- a few asymmetric organic accents
- enough restraint that the banner still reads clearly at repo scale
- a protected text-safe zone: no circles, blobs, strokes, or frames should sit behind or cut through the title or copy
- a clean gutter between the longest text line and the nearest decorative shape
- a default left-copy / right-illustration split unless the repo genuinely benefits from a different composition

## Family consistency

Across a family of skill repos:

- keep the badge grammar consistent
- keep the README section order close enough to feel related
- let colors and copy vary by repo lane
- keep each repo independently understandable
