# Release Notes – Version 1.0.0

**Release Date:** September 22, 2026 **Status:** ✨ Stable

---

## 🎯 Theme

**Initial Template Scaffold — AGENTS.md & Claude Code Skills**

Version 1.0.0 is this template's first release: a framework-agnostic `AGENTS.md`, a thin `CLAUDE.md` pointer to it,
eight ready-to-invoke Claude Code skills under `.claude/skills/` and baseline `.gitignore`/`.aiignore` ignore
patterns. `AGENTS.md` merges the framework-agnostic parts of the sibling `hpsc-web-vite` and `hpsc-web-springboot`
projects' own `AGENTS.md`/`.claude/skills/` — git workflow, release checklist, roadmap planning, directory tree
maintenance, documentation conventions and icon registry — into a single fill-in-template usable for any project,
whether it's built on Spring Boot, React or something else entirely.

---

## ⭐ Key Highlights

### 📚 AGENTS.md Conventions Template

- One cross-tool conventions file covering project overview, tech stack, build/run commands, environment variables,
  architecture, code quality & CI, documentation conventions (British English, serial commas, icon registry), the
  documentation file map, roadmap planning, Claude Code skills, test conventions, directory tree maintenance, the
  GitFlow git workflow and the release checklist — each section marked either *(reusable as-is)* or *(fill in)*/
  *(fill in, if applicable)* so a new project can adopt it without reconstructing the conventions from scratch
- `CLAUDE.md` kept as a thin pointer to `AGENTS.md`, existing only because Claude Code specifically looks for a file
  by that name

### 🧩 Eight Claude Code Skills

- `generate-commit-message`, `generate-pr-summary`, `prep-version-release`, `scaffold-integration-tests`,
  `scaffold-unit-tests`, `sync-improvement-plan-gaps`, `sync-unreleased-changes` and `update-improvement-plan-gaps`
  — each turns a workflow already described in `AGENTS.md` into a ready-to-invoke skill, so an agent doesn't have to
  reconstruct it from scratch every session

---

## 📦 What's New

### Added

#### Documentation

- `AGENTS.md`: the full cross-tool conventions template described above
- `CLAUDE.md`: thin pointer to `AGENTS.md`

#### Tooling

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

---

## 🚀 Migration Guide

This is the initial release — there is no previous version to migrate from.

---

## 📊 Statistics

- **Total Commits:** 5
- **Files Added:** 12
- **Insertions:** 2,128 lines
- **Deletions:** 0 lines
- **Claude Code Skills Added:** 8
- **Contributors:** 1

---

## 🧭 Design Notes

- **Merge, don't duplicate.** Rather than maintaining separate conventions files per stack, `AGENTS.md` extracts
  only the framework-agnostic parts common to both sibling projects, leaving stack-specific detail as explicit
  *(fill in)* scaffolding.
- **Mark every section's fill-in status explicitly.** Each `AGENTS.md` section is tagged *(reusable as-is)* or
  *(fill in)*/*(fill in, if applicable)*, so an agent adopting the template knows exactly what still needs
  project-specific detail versus what to keep verbatim.
- **Skills point back to AGENTS.md rather than restating it.** Every skill treats `AGENTS.md` as the single source
  of truth for conventions it automates, reading it in full before acting instead of duplicating its rules.

---

## 🧪 Testing

- No automated test suite — this is a documentation-only template with no source code to exercise.
- Manual review: every `AGENTS.md`/skill Markdown file checked against its own line-wrap rule (100–120 characters,
  tables/code blocks exempt).

---

## 🐛 Known Issues

- `README.md`, `ARCHITECTURE.md`, `CONTRIBUTING.md` and `LICENSE.md` — named in `AGENTS.md`'s own Documentation File
  Map — don't exist yet in this template; each is created when a project is actually scaffolded from it.
- No `documentation/roadmap/improvement-plan.md`/`improvement-plan-tasks.md` exists yet, so the
  `sync-improvement-plan-gaps`/`update-improvement-plan-gaps` skills have nothing to audit against until a project
  using this template creates them.

---

## 🔮 Future Enhancements

- Fill in the *(fill in)* scaffolding in `AGENTS.md` and each skill's `allowed-tools`/stack-specific steps once this
  template is used to scaffold an actual project.
- Add `README.md`, `ARCHITECTURE.md`, `CONTRIBUTING.md` and `LICENSE.md` templates alongside `AGENTS.md`/`CLAUDE.md`.

---

## 👥 Contributors

Leoni Lubbinge

---

## 📝 Notes

Version 1.0.0 establishes this repository as a standalone, reusable template — every convention that's genuinely
stack-agnostic lives in `AGENTS.md`, ready to be filled in for a specific project's tech stack.

---

**For detailed change history, see [CHANGELOG.md](/CHANGELOG.md)**

**For previous releases, see the [history folder](/documentation/history)**
