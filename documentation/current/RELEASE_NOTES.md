# Release Notes – Version 1.2.0

**Release Date:** September 24, 2026 **Status:** ✨ Stable

---

## 🎯 Theme

**Fill-In Template Scaffolds for the Full Documentation Set**

Version 1.2.0 is a documentation-only minor release. Until now, this template shipped only `AGENTS.md`, `CLAUDE.md`
and its Claude Code skills. The rest of the documentation set that `AGENTS.md`'s Documentation File Map describes
(`README.md`, `ARCHITECTURE.md`, `CONTRIBUTING.md`, `HISTORY.md`, `CHANGELOG.md`, `RELEASE_NOTES.md` and
`LICENSE.md`) was left for each new project to write from scratch. This release adds a fill-in-template scaffold for
every one of those files, plus optional `UI.md`, `PACKAGES.md` and `HELP.md` scaffolds for stack-specific docs and
`documentation/roadmap/` scaffolds for the improvement plan and its task list. To make room at the repository root,
the template's own `README.md`, `CHANGELOG.md`, `HISTORY.md` and `RELEASE_NOTES.md` move into
`documentation/current/`. The template also gets its own release history for the first time, backfilled for v1.0.0
and v1.1.0. `HISTORY.md`'s Evolution Overview is now always split out into
`documentation/history/EVOLUTION_OVERVIEW.md`, and roadmap headings across the scaffolds and skills now use the icons
`AGENTS.md`'s registry assigns them.

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
- `documentation/roadmap/improvement-plan.md`/`improvement-plan-tasks.md` scaffolds, combining the formats of
  `hpsc-web-springboot` and `hpsc-web-vite`'s own and using the section headings the
  `update-improvement-plan-gaps`/`sync-improvement-plan-gaps` skills expect

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

### ✍️ Heading Icons Aligned with the Registry

- Roadmap headings (`HISTORY.md`'s Future Roadmap Implications, `CONTRIBUTING.md`'s and `improvement-plan.md`'s
  Roadmap) now use `AGENTS.md`'s registered 🛤️ icon instead of a mix of 🗺️ and 🚀, and `improvement-plan.md`'s
  Success Criteria uses ☑️ instead of ✅, which the registry reserves for completed gap status
- The `update-improvement-plan-gaps`/`sync-improvement-plan-gaps` skills refer to those headings by the same icons
- Every other live heading was audited against the registry too, realigning `AGENTS.md`'s own Documentation
  Conventions heading (✍️), four `ARCHITECTURE.md` scaffold headings (🏛️, 🧭, 🔃, 🛠️), this template's own
  `README.md` What's Inside (📁) and the improvement-plan scaffold's At a Glance (🌳) and Related Documentation (🔗)
- The registry gains a `🔃 Data flow` entry, and its 🧪 entry now also covers the `### 🧪 [Unreleased]` CHANGELOG
  heading

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
- `documentation/roadmap/improvement-plan.md`, `documentation/roadmap/improvement-plan-tasks.md`: fill-in-template
  scaffolds for a scaffolded project's improvement plan and task list

### Changed

#### Documentation

- This template's own release archive grouped into `documentation/history/v1/`, adopting `AGENTS.md`'s optional
  per-major-version layout from its first releases
- `HISTORY.md`'s "📖 Evolution Overview" section is now always split out into
  `documentation/history/EVOLUTION_OVERVIEW.md`, with `AGENTS.md` and the `prep-version-release` skill updated to
  match
- `README.md`, `CHANGELOG.md`, `HISTORY.md` and `RELEASE_NOTES.md`: this template's own copies moved from the
  repository root into `documentation/current/`
- Roadmap headings standardised on `AGENTS.md`'s registered 🛤️ icon, and `improvement-plan.md`'s Success Criteria
  on ☑️, across the `HISTORY.md`/`CONTRIBUTING.md` scaffolds, this template's own `HISTORY.md` and the
  `improvement-plan.md` scaffold
- Remaining drifted headings realigned with the registry: `AGENTS.md`'s Documentation Conventions, the
  `ARCHITECTURE.md` scaffold's Core Architecture/Key Design Patterns/Data Flow/Development Guidelines, `README.md`'s
  What's Inside and the `improvement-plan.md` scaffold's At a Glance/Related Documentation
- `AGENTS.md` icon registry: new `🔃 Data flow` entry; 🧪 widened to "Testing / unreleased changes"

#### Tooling

- `.claude/skills/update-improvement-plan-gaps`, `.claude/skills/sync-improvement-plan-gaps`: heading references
  updated to the 🛤️/☑️ icons, and a serial-comma violation fixed in both

---

## 🚀 Migration Guide

No code, schema or dependency changes in this release. For a project already scaffolded from an earlier version:

- Optionally, compare the project's own `README.md`/`ARCHITECTURE.md`/`CONTRIBUTING.md`/`HISTORY.md`/`CHANGELOG.md`/
  `RELEASE_NOTES.md`/`LICENSE.md` against the new root-level scaffolds and pull forward any sections worth adopting.
- If the project's `HISTORY.md` still holds its Evolution Overview narrative inline, move it to
  `documentation/history/EVOLUTION_OVERVIEW.md` and leave a short pointer under the same heading/anchor, per the
  updated Documentation File Map.
- Copy `documentation/roadmap/` too, and fill it in last, since its improvement plan is synthesised from the rest
  of the documentation set.
- If the project's roadmap headings use 🗺️/🚀, or its Success Criteria heading uses ✅, switch them to 🛤️/☑️ and
  update the two improvement-plan skills to match. Likewise re-check any heading copied from the earlier
  `ARCHITECTURE.md` scaffold (Core Architecture, Key Design Patterns, Data Flow, Development Guidelines) against the
  updated registry.
- Don't copy `documentation/current/`. It holds this template repository's own docs, not scaffolds.

---

## 📊 Statistics

- **Total Commits:** 23
- **Files Changed:** 26
- **Insertions:** 2,039 lines
- **Deletions:** 36 lines
- **Net Change:** +2,003 lines

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
- **Let the icon registry decide, not the sibling projects.** `hpsc-web-springboot` and `hpsc-web-vite` disagree on
  their roadmap and success-criteria icons. The scaffolds follow `AGENTS.md`'s own registry instead, and the skills
  that look for those headings by name were updated in the same change.

---

## 🧪 Testing

- No automated test suite — this is a documentation-only template.
- Manual line-wrap check (100–120 characters, tables/code blocks exempt) across every changed file.
- Manual review confirming every root-level scaffold's *(fill in)*/*(reusable as-is)* markers and the
  `documentation/current/` link paths resolve.

---

## 🐛 Known Issues

- `documentation/roadmap/` now holds fill-in-template scaffolds, but this template still has no improvement plan of
  its own (carried over from v1.0.0), so the `update-improvement-plan-gaps`/`sync-improvement-plan-gaps` skills have
  nothing real to audit here.
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
