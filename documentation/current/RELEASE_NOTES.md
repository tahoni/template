# Release Notes – Version 1.2.0

**Release Date:** September 24, 2026 **Status:** ✨ Stable

---

## 🎯 Theme

**Fill-In Template Scaffolds for the Full Documentation Set**

Version 1.2.0 is a documentation-only minor release. Until now, this template shipped only `AGENTS.md`, `CLAUDE.md`
and its Claude Code skills. The rest of the documentation set that `AGENTS.md`'s Documentation File Map describes
(`README.md`, `ARCHITECTURE.md`, `CONTRIBUTING.md`, `HISTORY.md`, `CHANGELOG.md`, `RELEASE_NOTES.md` and
`LICENSE.md`) was left for each new project to write from scratch. This release adds a fill-in-template scaffold for
every one of those files, plus optional `UI.md`, `PACKAGES.md` and `HELP.md` scaffolds for stack-specific docs. To make
room for them at the repository root, the template's own `README.md`, `CHANGELOG.md`, `HISTORY.md` and
`RELEASE_NOTES.md` move into `documentation/current/`. The template also gets its own release history for the first
time, backfilled for v1.0.0 and v1.1.0. `HISTORY.md`'s Evolution Overview is now always split out into
`documentation/history/EVOLUTION_OVERVIEW.md`.

---

## ⭐ Key Highlights

### 📜 Fill-In Template Scaffolds

- `README.md`, `ARCHITECTURE.md`, `CONTRIBUTING.md`, `HISTORY.md`, `CHANGELOG.md` and `RELEASE_NOTES.md` scaffolds at
  the repository root, each marking its sections *(reusable as-is)* or *(fill in)* the same way `AGENTS.md` does,
  with `{{placeholder}}` tokens for project-specific values
- `LICENSE.md` scaffold: MIT licence text with `{{year}}`/`{{copyright holder}}` placeholders, to swap for a
  different licence entirely where the project uses one
- Optional `UI.md` (from `hpsc-web-vite`), `PACKAGES.md` (from `hpsc-web-vite`) and `HELP.md` (from
  `hpsc-web-springboot`) scaffolds for the stack-specific docs the Documentation File Map already named, each to be
  deleted rather than filled in where it doesn't apply

### 🗺️ Template's Own Docs Move to documentation/current/

- The template's own `README.md`, `CHANGELOG.md`, `HISTORY.md` and `RELEASE_NOTES.md` now live in
  `documentation/current/`, so the root-level names belong to the scaffolds a new project copies
- The template's own release history is backfilled for v1.0.0 and v1.1.0, with archives grouped into
  `documentation/history/v1/`

### 📖 Evolution Overview Always Split Out

- `HISTORY.md`'s "📖 Evolution Overview" section is now always a short pointer to
  `documentation/history/EVOLUTION_OVERVIEW.md`, from a project's very first release onward. Before, the split was an
  optional step for once `HISTORY.md` grew too large. `AGENTS.md`'s Documentation File Map and Release Checklist, and
  the `prep-version-release` skill, now say to write every new Phase entry there

---

## 📦 What's New

### Added

#### Documentation

- `README.md`: project overview, repository/issues links, a "What's Inside" table of this template's files, a
  Getting Started walkthrough for scaffolding a new project from it, a Documentation table and an Author section
- `CHANGELOG.md`, `HISTORY.md`, `RELEASE_NOTES.md` and `documentation/history/v1/`: this template's own release
  documentation, backfilled for v1.0.0 and v1.1.0 from the existing commit history and `v1.0.0`/`v1.1.0` tags
- `README.md`, `ARCHITECTURE.md`, `CONTRIBUTING.md`, `HISTORY.md`, `CHANGELOG.md`, `RELEASE_NOTES.md`:
  fill-in-template scaffolds at the repository root for a scaffolded project's own copies of these files
- `LICENSE.md`: fill-in-template MIT licence with `{{year}}`/`{{copyright holder}}` placeholders
- `UI.md`, `PACKAGES.md` and `HELP.md`: optional fill-in-template scaffolds for stack-specific docs

### Changed

#### Documentation

- This template's own release archive grouped into `documentation/history/v1/`, adopting `AGENTS.md`'s optional
  per-major-version layout from its first releases
- `HISTORY.md`'s "📖 Evolution Overview" section is now always split out into
  `documentation/history/EVOLUTION_OVERVIEW.md`, with `AGENTS.md` and the `prep-version-release` skill updated to
  match
- `README.md`, `CHANGELOG.md`, `HISTORY.md` and `RELEASE_NOTES.md`: this template's own copies moved from the
  repository root into `documentation/current/`

---

## 🚀 Migration Guide

No code, schema or dependency changes in this release. For a project already scaffolded from an earlier version:

- Optionally, compare the project's own `README.md`/`ARCHITECTURE.md`/`CONTRIBUTING.md`/`HISTORY.md`/`CHANGELOG.md`/
  `RELEASE_NOTES.md`/`LICENSE.md` against the new root-level scaffolds and pull forward any sections worth adopting.
- If the project's `HISTORY.md` still holds its Evolution Overview narrative inline, move it to
  `documentation/history/EVOLUTION_OVERVIEW.md` and leave a short pointer under the same heading/anchor, per the
  updated Documentation File Map.
- Don't copy `documentation/current/`. It holds this template repository's own docs, not scaffolds.

---

## 📊 Statistics

- **Total Commits:** 14
- **Files Changed:** 21
- **Insertions:** 1,658 lines
- **Deletions:** 22 lines
- **Net Change:** +1,636 lines

---

## 🧭 Design Notes

- **Scaffold every file the Documentation File Map names.** `AGENTS.md` already told a new project which docs to
  keep, but a new project still had to write each one from nothing. Shipping a scaffold for each of them turns the
  map from a description into a starting point.
- **Separate the template's own docs from the scaffolds.** A template repository needs real docs of its own and also
  root-level scaffolds with the same filenames. Moving the template's own copies into `documentation/current/` lets
  a new project copy the root as-is, without mixing up the two.
- **Delete optional scaffolds rather than leaving them unfilled.** `UI.md`, `PACKAGES.md` and `HELP.md` each apply
  to only some stacks. Each one says so in its own template note, so an unfilled copy doesn't linger in a project
  where it doesn't fit.
- **Split the Evolution Overview out by construction.** `hpsc-web-springboot` only split its Evolution Overview out
  once it had grown to roughly half of `HISTORY.md`. Splitting it out from the first release means that one-off
  reorganisation is never needed.

---

## 🧪 Testing

- No automated test suite — this is a documentation-only template.
- Manual line-wrap check (100–120 characters, tables/code blocks exempt) across every changed file.
- Manual review confirming every root-level scaffold's *(fill in)*/*(reusable as-is)* markers and the
  `documentation/current/` link paths resolve.

---

## 🐛 Known Issues

- No `documentation/roadmap/improvement-plan.md`/`improvement-plan-tasks.md` exists yet for this template (carried
  over from v1.0.0), so the `update-improvement-plan-gaps`/`sync-improvement-plan-gaps` skills have nothing to audit.
- The template repository still has no `ARCHITECTURE.md`, `CONTRIBUTING.md` or `LICENSE.md` of its own. The
  root-level files with those names are scaffolds for scaffolded projects.
- The `documentation/history/v1/` archives for v1.0.0 and v1.1.0 had their internal links updated for the
  `documentation/current/` move, so they are no longer byte-for-byte copies of the release notes as first written.

---

## 🔮 Future Enhancements

- Keep syncing genuinely reusable conventions and scaffolds back from `hpsc-web-vite`/`hpsc-web-springboot` as they
  evolve.
- Add a `documentation/roadmap/` improvement plan for the template itself.

---

## 👥 Contributors

Leoni Lubbinge

---

## 📝 Notes

Version 1.2.0 turns this template from a conventions file with automation into a complete documentation kit. A new
project now gets a starting point for every file `AGENTS.md` asks it to maintain.

---

**For detailed change history, see [CHANGELOG.md](/documentation/current/CHANGELOG.md)**

**For previous releases, see the [history folder](/documentation/history)**
