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

---

## 🗺️ Future Roadmap Implications

- Continue periodically diffing `hpsc-web-vite`/`hpsc-web-springboot`'s own `AGENTS.md`/skill history against this
  template's last sync point, pulling forward genuinely reusable conventions.
- Once this template is actually used to scaffold a project, fill in its *(fill in)* scaffolding and add the
  `README.md`/`ARCHITECTURE.md`/`CONTRIBUTING.md`/`LICENSE.md` files its own Documentation File Map already
  describes.

---

## 🎓 Conclusion

Two releases in, this template's shape is already clear: a single `AGENTS.md` as the source of truth, a thin
`CLAUDE.md` pointer and a set of Claude Code skills that automate its conventions without ever restating them.
Keeping it synced with the sibling projects it was combined from — pulling forward what's genuinely reusable,
leaving out what's project-specific — is the core discipline this history is meant to keep visible.

---

**For the current release, see [RELEASE_NOTES.md](RELEASE_NOTES.md)**

**For the full change log, see [CHANGELOG.md](CHANGELOG.md)**
