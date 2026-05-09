# CLAUDE.md

## Repository Purpose

This is the **GitHub Organization Health repository** for the `jfandy1982` organization. It provides default community health files (issue templates, PR templates, CODEOWNERS, labels) and shared tooling configuration that applies to all repos in the organization.

The nested `.github/` structure is intentional: GitHub reads community health files from `.github/` within this repo.

## Known Structure

- `.github/` — GitHub community health files (templates, workflows, CODEOWNERS, repository-specific renovate.json)
- `renovate-base.json` — shared Renovate base config, extended by all org repos
- `SECURITY.md` — exists in repo root (work in progress, placeholder content is intentional)
- `experiments/` — deliberate playground and backup directory, not production code; ignore when reviewing
  - `experiments/superpowers/` — brainstorming specs and implementation plans from Claude sessions (gitignored, local only); check here for prior design decisions before starting new work
- `node_modules/` — exists locally but is gitignored; not committed to the repo

## Tooling

- GitHub Actions SHAs are manually verified and pinned — do not flag pinned SHAs as outdated without checking first
- Renovate: `renovate.json` in `.github/` is the repository-specific Renovate entry point; the `schedule` override there is intentional
- pre-commit hook runs `lint-staged` (Prettier + cspell) on `*.json`, `*.md`, `*.yml`
