# Template History

A historical overview of this template's evolution from its initial scaffold to the current release, documenting
how its `AGENTS.md` conventions and Claude Code skills have grown over time.

---

## Table of Contents

- [📅 Historical Timeline](#-historical-timeline)
- [📖 Evolution Overview](#-evolution-overview)
- [📚 Key Learnings](#-key-learnings)
- [🗺️ Future Roadmap Implications](#-future-roadmap-implications)
- [🎓 Conclusion](#-conclusion)

---

## 📅 Historical Timeline

### Version 1.2.0 (September 24, 2026)

**Theme:** Fill-In Template Scaffolds for the Full Documentation Set

**Key Focus:**

- Fill-in-template scaffolds added at the repository root for every file `AGENTS.md`'s Documentation File Map
  names: `README.md`, `ARCHITECTURE.md`, `CONTRIBUTING.md`, `HISTORY.md`, `CHANGELOG.md`, `RELEASE_NOTES.md` and
  an MIT `LICENSE.md` with placeholders
- Optional `UI.md` and `PACKAGES.md` (from `hpsc-web-vite`) and `HELP.md` (from `hpsc-web-springboot`) scaffolds
  added for stack-specific docs, each to be deleted rather than filled in where it doesn't apply
- This template's own `README.md`, `CHANGELOG.md`, `HISTORY.md` and `RELEASE_NOTES.md` moved into
  `documentation/current/` to free the root names for the scaffolds. Its release history was backfilled for v1.0.0
  and v1.1.0, with archives grouped into `documentation/history/v1/`
- `HISTORY.md`'s Evolution Overview is now always split out into `documentation/history/EVOLUTION_OVERVIEW.md`
  from the first release onward, with `AGENTS.md` and the `prep-version-release` skill updated to match

### Version 1.1.0 (September 23, 2026)

**Theme:** Sync Optional documentation/history/vN/ Layout & Layered Test Conventions from hpsc-web-springboot

**Key Focus:**

- `AGENTS.md`'s Documentation File Map and Release Checklist document an optional per-major-version
  `documentation/history/v<major>/` subdirectory grouping and a companion `EVOLUTION_OVERVIEW.md` split for an
  oversized `HISTORY.md`, both pulled forward from the sibling `hpsc-web-springboot` project
- `AGENTS.md`'s Test Conventions section formalises an optional three-tier layered test architecture
  (interface-contract test, impl-only-helper test, no-mock integration test), previously only implicit in the
  `scaffold-unit-tests`/`scaffold-integration-tests` skills
- `generate-pr-summary`, `prep-version-release` and `update-improvement-plan-gaps` skills updated to read/write the
  optional `documentation/history/v<major>/...` path
- Serial-comma violations fixed in `AGENTS.md` and `scaffold-integration-tests/SKILL.md`

### Version 1.0.0 (September 22, 2026)

**Theme:** Initial Template Scaffold — AGENTS.md & Claude Code Skills

**Key Focus:**

- `AGENTS.md` established as the single cross-tool conventions file, merging the framework-agnostic parts of the
  sibling `hpsc-web-vite` and `hpsc-web-springboot` projects' own `AGENTS.md`/`.claude/skills/` into a
  fill-in-template usable for any project
- `CLAUDE.md` added as a thin pointer to `AGENTS.md`
- Eight Claude Code skills added under `.claude/skills/`: `generate-commit-message`, `generate-pr-summary`,
  `prep-version-release`, `scaffold-integration-tests`, `scaffold-unit-tests`, `sync-improvement-plan-gaps`,
  `sync-unreleased-changes` and `update-improvement-plan-gaps`
- Commit-message format and `CHANGELOG.md` heading depth hard-coded across the git-workflow skills to match
  `AGENTS.md` exactly, instead of hedging between two conventions
- Every skill trimmed down to a pointer at the relevant `AGENTS.md` section for any convention it shares with
  `AGENTS.md`, rather than restating it, keeping only its own unique procedural mechanics

---

## 📖 Evolution Overview

The full Phase-by-phase narrative behind this template's evolution lives in
[`documentation/history/EVOLUTION_OVERVIEW.md`](/documentation/history/EVOLUTION_OVERVIEW.md), split out to keep
this file a manageable size.

---

## 📚 Key Learnings

- **A template drifts the moment its source projects keep evolving without it.** Treating
  `hpsc-web-vite`/`hpsc-web-springboot` as living sources to periodically re-sync from, rather than a one-time
  extraction, is what keeps this template's conventions from going stale.
- **Mark every borrowed convention as optional unless the template's own baseline case needs it.** The
  `documentation/history/vN/` grouping only matters once a project's archive grows large — documenting it as an
  opt-in scaling step, rather than the default, keeps a freshly scaffolded project's `documentation/history/`
  simple.
- **A skill that restates a convention instead of pointing at it will eventually contradict it.** Every skill in
  this template treats `AGENTS.md` as the single source of truth it defers to, a discipline established in v1.0.0
  and reinforced by v1.1.0's own skill updates.
- **A template's own docs and its scaffolds need separate homes.** Once the template shipped root-level scaffolds
  with the same filenames as its own real docs, v1.2.0 moved the real ones into `documentation/current/`. That way
  a new project can copy the root as-is without inheriting the template's own history.
- **Make a scaling step the default when it costs nothing up front.** Splitting the Evolution Overview out of
  `HISTORY.md` from the first release, rather than once it grows large, removes a disruptive reorganisation later.
  An empty pointer section costs a new project almost nothing.

---

## 🗺️ Future Roadmap Implications

- Continue periodically diffing `hpsc-web-vite`/`hpsc-web-springboot`'s own `AGENTS.md`/skill history against this
  template's last sync point, pulling forward genuinely reusable conventions.
- With a scaffold now shipped for every file in the Documentation File Map, check each new convention pulled
  forward from the sibling projects against both `AGENTS.md` and the matching root-level scaffold, so the two don't
  drift apart.
- Add a `documentation/roadmap/` improvement plan for the template itself, so the
  `update-improvement-plan-gaps`/`sync-improvement-plan-gaps` skills have something to audit during its own
  releases.

---

## 🎓 Conclusion

Three releases in, this template's shape is clear: a single `AGENTS.md` as the source of truth, a thin `CLAUDE.md`
pointer, a set of Claude Code skills that automate its conventions without ever restating them and, since v1.2.0, a
fill-in-template scaffold for every documentation file those conventions ask a project to maintain.
Keeping it synced with the sibling projects it was combined from — pulling forward what's genuinely reusable,
leaving out what's project-specific — is the core discipline this history is meant to keep visible.

---

**For the current release, see [RELEASE_NOTES.md](RELEASE_NOTES.md)**

**For the full change log, see [CHANGELOG.md](CHANGELOG.md)**
