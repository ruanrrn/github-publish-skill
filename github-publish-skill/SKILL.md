---
name: github-publish-skill
description: "Publish or republish an OpenClaw skill as a complete public GitHub skill repository. Use when: (1) creating a new public repo for a reusable skill, (2) republishing an existing skill after updates, (3) standardizing README, CONTRIBUTING, repo metadata, and social-preview assets for a skill repo. This skill's public-repo standard applies only to skill repositories, not to arbitrary software projects or general GitHub repos."
---

# GitHub Publish Skill

Publish an OpenClaw skill to GitHub like a finished artifact instead of a folder dump.

## Scope

Use this skill only for skill repositories.

That means repos whose main payload is an OpenClaw skill package, typically including:

- `<skill-name>/SKILL.md`
- `dist/<skill-name>.skill`
- optional skill resources such as `references/`, `scripts/`, or `assets/`

Do not use this skill as a generic GitHub beautifier for arbitrary codebases, libraries, apps, or mixed-purpose repos.

## What this skill owns

This skill combines two responsibilities:

1. publish or republish a skill repo to GitHub
2. shape that repo so it looks complete, standalone, and reusable as a public skill repo

## Publish workflow

### 1. Validate the skill

Before publishing, ensure:

- `SKILL.md` exists and has valid `name` + `description` frontmatter
- bundled references or assets resolve correctly
- the skill packages cleanly into `.skill`

### 1.5 Run a secret risk scan (mandatory)

Before creating commits or pushing to a public repo, scan for obvious secrets.

Minimum requirements:

- scan tracked + untracked files in the repo payload (exclude `.git/` and `dist/`)
- fail closed: if anything looks like a secret, stop and ask before pushing
- never paste secret values into chat or commit messages; report only file + line

Recommended tooling:

- run `python3 scripts/secret_scan.py <repo-root>` from this skill repo's `scripts/` directory
- also sanity-check that files like `.env`, `*.pem`, `*.key`, `id_rsa`, and `id_ed25519` are not present

If the scan flags findings:

- remove the secret from the repo
- rotate/revoke the credential if it may have been exposed
- add/verify `.gitignore` rules so it cannot happen again

### 2. Prepare the repo payload

A polished public skill repo should usually include:

- `README.md`
- `README.zh-CN.md`
- `LICENSE`
- `CONTRIBUTING.md`
- `dist/<skill>.skill`
- `<skill>/SKILL.md`
- `assets/social-preview.svg` when public presentation matters

### 3. Create or update the GitHub repo

Typical local flow:

```bash
cd /root/.openclaw/workspace/repos
mkdir -p <repo-name>/dist
cp -R /root/.openclaw/workspace/skills/<skill-name> <repo-name>/
python3 /root/.nvm/versions/node/v22.22.0/lib/node_modules/openclaw/skills/skill-creator/scripts/package_skill.py \
  /root/.openclaw/workspace/skills/<skill-name> \
  /root/.openclaw/workspace/dist
cp /root/.openclaw/workspace/dist/<skill-name>.skill <repo-name>/dist/
```

Then initialize or update git and push with `gh`.

### 4. Set GitHub metadata

Keep metadata aligned with the skill's real scope:

- description should match the skill trigger language and README
- topics should be concise and family-consistent
- default branch should be `main`

### 5. Republish cleanly

On updates:

- sync the skill source into the repo
- regenerate the `.skill` artifact
- refresh README or assets if the public behavior changed
- commit and push with a descriptive message

## Public skill repo style

The public style guidance in this skill applies only to skill repositories.

If a repo is not primarily a distributable OpenClaw skill repo, stop and use a different standard.

### README structure

Default structure:

1. title
2. language switcher
3. banner image
4. badge row
5. one-sentence description
6. optional scope callout for hard-boundary repos
7. `Overview`
8. `Why this exists`
9. `Scope`
10. `What the standard covers` or another repo-specific capability section
11. `Workflow summary` when the repo defines an operational workflow
12. `When to use it`
13. representative examples or outcomes
14. `Related skill repos` marked as optional examples, not required dependencies
15. `Install`
16. `What this repo contains`
17. `Social preview`
18. `Repository layout`
19. `Contributing`
20. `Release hygiene`
21. `Repository`

### README voice

Write like a serious open-source tool, not an internal note dump and not marketing fluff.

Aim for:

- precise positioning in the first sentence
- professional, public-facing prose that can survive being read cold on GitHub
- explicit scope boundaries instead of relying on implication
- examples framed as representative outcomes, not casual chat transcripts unless the repo genuinely needs raw transcript style
- short, information-dense paragraphs instead of slogan piles
- bilingual parity when both `README.md` and `README.zh-CN.md` exist

### Badge pattern

Use a small consistent badge set near the top.

Typical badges:

- `OpenClaw Skill`
- `Focus-...`
- `Works-Standalone`
- `Artifact-.skill Included`
- `License-MIT`

Optional badges:

- `README-Bilingual`
- a lane-specific capability badge when it adds clarity

### Social preview rule

Each public skill repo should have:

- `assets/social-preview.svg`
- a short one-line social preview copy snippet in the README
- a banner that stays text-first and readable at repo scale
- a protected text-safe area where no decorative element sits behind, crosses, or crowds the copy
- no meaningless right-side illustration filler; if decoration adds no information or mood, omit it
- a minimal composition that can succeed with typography, spacing, and color alone

Document the GitHub limitation honestly:

- the public `gh` CLI and GraphQL `UpdateRepositoryInput` do not expose a writable custom social preview field
- if the repo should use that image in GitHub's settings UI, say so directly in the README

### CONTRIBUTING rule

Keep `CONTRIBUTING.md` short and repo-specific.

It should explain:

- what changes belong in the repo
- what changes do not
- whether `.skill` artifacts must be regenerated after material changes
- what a good PR should explain
- the repo's role inside its skill family

## Family rule

When multiple public repos belong to one skill family:

- keep them visually related
- keep each repo independently useful
- treat related repos as optional companions, not hidden dependencies
- let the umbrella repo be broader without making smaller repos look incomplete

## References

Read `references/public-skill-style.md` when shaping README, badges, CONTRIBUTING, and social-preview sections.
