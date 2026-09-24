# AllTemplates Template

## 🧾 Change Log

All notable changes to this template are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/), and this project adheres to
[Semantic Versioning](https://semver.org/spec/v2.0.0.html).

---

### Table of Contents

- [🧪 Unreleased](#-unreleased)
- [🧾 Version 1.2.0](#-120---2026-09-24) ← Current
- [🧾 Version 1.1.0](#-110---2026-09-23)
- [🧾 Version 1.0.0](#-100---2026-09-22)

---

### 🧪 [Unreleased]

### 🧾 [1.2.0] - 2026-09-24

#### ➕ Added

##### Documentation

- `README.md`: project overview, repository/issues links, a "What's Inside" table of this template's files, a
  Getting Started walkthrough for scaffolding a new project from it, a Documentation table and an Author section
- `CHANGELOG.md`, `HISTORY.md`, `RELEASE_NOTES.md` and `documentation/history/v1/`: this template's own release
  documentation, backfilled for v1.0.0 and v1.1.0 from the existing commit history and `v1.0.0`/`v1.1.0` tags
- `README.md`, `ARCHITECTURE.md`, `CONTRIBUTING.md`, `HISTORY.md`, `CHANGELOG.md`, `RELEASE_NOTES.md`:
  fill-in-template scaffolds at the repository root for a scaffolded project's own copies of these files, each
  marking its sections *(reusable as-is)* or *(fill in)* and using `{{placeholder}}` tokens for project-specific
  values, per `AGENTS.md`'s Documentation File Map
- `LICENSE.md`: fill-in-template MIT licence with `{{year}}`/`{{copyright holder}}` placeholders, to swap for a
  different licence entirely where the project uses one
- `UI.md` (based on `hpsc-web-vite`'s own), `PACKAGES.md` (based on `hpsc-web-vite`'s own) and `HELP.md` (based on
  `hpsc-web-springboot`'s own): optional fill-in-template scaffolds for the stack-specific docs `AGENTS.md`'s
  Documentation File Map already names — each to be deleted rather than filled in where it doesn't apply
- `documentation/roadmap/improvement-plan.md`, `documentation/roadmap/improvement-plan-tasks.md`: fill-in-template
  scaffolds for a scaffolded project's improvement plan and task list, combining the formats of `hpsc-web-springboot`
  and `hpsc-web-vite`'s own, with the section headings the `update-improvement-plan-gaps`/
  `sync-improvement-plan-gaps` skills expect (`🛤️ Roadmap`, `☑️ Success Criteria`); `README.md`'s What's Inside table
  and Getting Started steps updated to include them

#### 🔄 Changed

##### Documentation

- This template's own release archive grouped into `documentation/history/v1/`, adopting `AGENTS.md`'s optional
  per-major-version layout from its first releases
- `HISTORY.md`'s "📖 Evolution Overview" section split out into new `documentation/history/EVOLUTION_OVERVIEW.md`
  — previously an optional step for once `HISTORY.md` grew too large, now always split out from the first release
  onward. `HISTORY.md` keeps a short pointer under the same heading/anchor, so its Table of Contents entry still
  resolves; `AGENTS.md`'s Documentation File Map and Release Checklist, and the `prep-version-release` skill's
  "Extend `HISTORY.md`" step, updated to match
- `README.md`, `CHANGELOG.md`, `HISTORY.md` and `RELEASE_NOTES.md`: this template's own copies moved from the
  repository root into `documentation/current/`, freeing the root names for the fill-in-template scaffolds a new
  project copies; internal links in `EVOLUTION_OVERVIEW.md` and the `documentation/history/v1/` archives updated to
  the new paths
- Roadmap headings standardised on `AGENTS.md`'s registered 🛤️ icon, replacing a mix of 🗺️ (reserved for the
  documentation file map) and 🚀 (reserved for getting started): `HISTORY.md`'s Future Roadmap Implications section
  (both the root scaffold and this template's own copy), `CONTRIBUTING.md`'s Roadmap section and the
  `improvement-plan.md` scaffold's Roadmap section
- `improvement-plan.md` scaffold's Success Criteria section switched from ✅ (reserved for completed roadmap gap
  status) to `AGENTS.md`'s registered ☑️ Checklist icon, matching `hpsc-web-vite`'s own improvement plan

##### Tooling

- `.claude/skills/update-improvement-plan-gaps`, `.claude/skills/sync-improvement-plan-gaps`: references to the
  improvement plan's Roadmap table and `HISTORY.md`'s Future Roadmap Implications section updated to the 🛤️ icon,
  and to its Success Criteria list updated to the ☑️ icon
- Fixed a serial-comma violation in both skills' "Goals & Constraints table, Roadmap table and Success Criteria
  list" step, which carried a comma before the final `and`, contradicting `AGENTS.md`'s own Serial Commas convention

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
