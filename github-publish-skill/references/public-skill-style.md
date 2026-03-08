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

One-sentence repository description.

> [!IMPORTANT]
> Optional hard-boundary callout when the repo standard applies only to a narrow class of repositories.
```

Optional:

- bilingual badge for multilingual repos
- omit the callout when the repo does not need boundary reinforcement at the top

## Required narrative sections

- `Overview`
- `Why this exists`
- `Scope`
- a repo-specific capability section such as `What the standard covers`
- `Workflow summary` when the repo defines a repeatable operational flow
- `When to use it`
- representative examples or outcomes
- `Related skill repos`
- `Install`
- `What this repo contains`
- `Social preview`
- `Repository layout`
- `Contributing`
- `Release hygiene`
- `Repository`

## README voice

Write for a public GitHub reader who has no private context.

Prefer:

- a precise opening sentence that says what the repo does
- professional product-documentation language over slogans or in-jokes
- explicit scope statements for narrow repos
- representative outcomes and workflows over vague claims
- bilingual consistency when the repo ships `README.md` and `README.zh-CN.md`

Avoid:

- chatty filler that weakens the repo's credibility
- internal shorthand that only makes sense to people already in the project
- overselling a narrow skill as a universal framework

## Related-skills wording

Use wording like:

- "These repositories are related examples, not required dependencies"
- "Start here when the problem is publishing the repository itself"
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

Prefer text-first banners over decorative filler. If the visual idea is not pulling its weight, remove it.

Aim for:

- a clear mood
- a strong text area
- enough restraint that the banner still reads clearly at repo scale
- a protected text-safe zone: no circles, blobs, strokes, or frames should sit behind or cut through the title or copy
- typography, spacing, and color doing most of the work
- zero obligation to add a right-side illustration block just to avoid empty space

## Family consistency

Across a family of skill repos:

- keep the badge grammar consistent
- keep the README section order close enough to feel related
- let colors and copy vary by repo lane
- keep each repo independently understandable
