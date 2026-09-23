# AllTemplates Template

## 🧾 Change Log

All notable changes to this template are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/), and this project adheres to
[Semantic Versioning](https://semver.org/spec/v2.0.0.html).

---

### Table of Contents

- [🧪 Unreleased](#-unreleased)
- [🧾 Version 1.1.0](#-110---2026-09-23) ← Current
- [🧾 Version 1.0.0](#-100---2026-09-22)

---

### 🧪 [Unreleased]

### 🧾 [1.1.0] - 2026-09-23

#### 🔄 Changed

##### Documentation

- `AGENTS.md`: Documentation File Map now describes an optional `documentation/history/v<major>/` subdirectory
  grouping (e.g. `documentation/history/v8/RELEASE_NOTES_v8.6.0.md`) for projects whose release archive grows
  large, plus a companion `documentation/history/EVOLUTION_OVERVIEW.md` split for an oversized `HISTORY.md`
- `AGENTS.md`: Release Checklist's archive-`RELEASE_NOTES.md`/write-PR-description steps reference the same
  optional `v<major>/` location
- `AGENTS.md`: Test Conventions section formalises an optional three-tier layered test architecture
  (interface-contract test, impl-only-helper test, no-mock integration test) for layered, interface-based backends
- Fixed serial-comma violations in `AGENTS.md` and `.claude/skills/scaffold-integration-tests/SKILL.md` — a
  handful of three-item lists carried a comma before the final `and`/`or`, contradicting `AGENTS.md`'s own Serial
  Commas convention

##### Tooling

- `.claude/skills/generate-pr-summary`, `.claude/skills/prep-version-release`,
  `.claude/skills/update-improvement-plan-gaps`: updated to read/write archived release docs at the optional
  `documentation/history/v<major>/...` path alongside the existing flat one

### 🧾 [1.0.0] - 2026-09-22

#### ➕ Added

##### Documentation

- `AGENTS.md`: cross-tool conventions template covering project overview, tech stack, build/run commands,
  environment variables, architecture, code quality & CI, documentation conventions, documentation file map,
  roadmap planning, Claude Code skills, test conventions, directory tree maintenance, git workflow (GitFlow) and
  the release checklist — merging the framework-agnostic parts of the `hpsc-web-vite` and `hpsc-web-springboot`
  sibling projects' own `AGENTS.md`/`.claude/skills/` into a single fill-in-template usable for any project
- `CLAUDE.md`: thin pointer to `AGENTS.md`, kept only because Claude Code specifically looks for a file by that
  name

##### Tooling

- `.claude/skills/generate-commit-message`: drafts a commit message and matching `CHANGELOG.md` entry for the
  current working tree changes
- `.claude/skills/generate-pr-summary`: condenses a version's `PR_DESCRIPTION.md`/`RELEASE_NOTES.md` into a very
  short, Bitbucket-style PR summary
- `.claude/skills/prep-version-release`: prepares a new version release — `RELEASE_NOTES.md`, `CHANGELOG.md`,
  `HISTORY.md`, reverse-synced docs and a draft release PR description — following `AGENTS.md`'s Release Checklist
- `.claude/skills/scaffold-integration-tests`: scaffolds integration tests exercising a target through its real
  internal wiring, not isolated/mocked collaborators
- `.claude/skills/scaffold-unit-tests`: scaffolds unit tests for a component/class/function/helper, isolated from
  its heavier/third-party dependencies
- `.claude/skills/sync-improvement-plan-gaps`: checks the current branch's changes against
  `documentation/roadmap/improvement-plan.md`'s tracked gaps and marks any closed/progressed
- `.claude/skills/sync-unreleased-changes`: audits the current branch's diff and ensures every notable change is
  reflected in `CHANGELOG.md`'s Unreleased section
- `.claude/skills/update-improvement-plan-gaps`: audits the codebase against `improvement-plan.md`/
  `improvement-plan-tasks.md` and records any newly identified gaps
- `.gitignore`, `.aiignore`: baseline ignore patterns for the template
