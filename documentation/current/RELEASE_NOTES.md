# Release Notes – Version 1.1.0

**Release Date:** September 23, 2026 **Status:** ✨ Stable

---

## 🎯 Theme

**Sync Optional documentation/history/vN/ Layout & Layered Test Conventions from hpsc-web-springboot**

Version 1.1.0 is a documentation-only minor release. It pulls two conventions forward from the sibling
`hpsc-web-springboot` project, which had evolved past the point this template was last combined from it: the
optional per-major-version `documentation/history/v<major>/` subdirectory grouping (with a companion
`EVOLUTION_OVERVIEW.md` split for an oversized `HISTORY.md`), and a formal three-tier layered test architecture for
interface-based backends. Three skills that reference the archive path are updated to match, and a handful of
serial-comma violations are corrected along the way.

---

## ⭐ Key Highlights

### 🗂️ Optional documentation/history/vN/ Layout

- `AGENTS.md`'s Documentation File Map now documents an optional `v<major>/` subdirectory grouping for
  `documentation/history/` (e.g. `documentation/history/v8/RELEASE_NOTES_v8.6.0.md`), to adopt once a project's
  release archive grows large enough to make browsing it unwieldy — plus a companion pattern of splitting an
  oversized `HISTORY.md`'s narrative into a standing `documentation/history/EVOLUTION_OVERVIEW.md` file
- The Release Checklist's archive/PR-description steps, and the `generate-pr-summary`, `prep-version-release` and
  `update-improvement-plan-gaps` skills, all updated to read/write that optional path alongside the existing flat
  one

### 🧪 Layered Test Architecture

- `AGENTS.md`'s Test Conventions section formalises an optional three-tier layered test architecture for a
  layered, interface-based backend: a unit test of the interface's own public contract (fully mocked), a separate
  unit test for implementation-only helper methods (also fully mocked) and a no-mock integration test of the same
  public contract through the real, framework-wired implementation — previously only implicit in the
  `scaffold-unit-tests`/`scaffold-integration-tests` skills

---

## 📦 What's New

### Changed

#### Documentation

- `AGENTS.md`: Documentation File Map describes the optional `documentation/history/v<major>/` subdirectory
  grouping and the companion `EVOLUTION_OVERVIEW.md` split for `HISTORY.md`
- `AGENTS.md`: Release Checklist's archive-`RELEASE_NOTES.md`/write-PR-description steps reference the same
  optional `v<major>/` location
- `AGENTS.md`: Test Conventions section formalises the optional three-tier layered test architecture
  (interface-contract test, impl-only-helper test, no-mock integration test)
- Fixed serial-comma violations in `AGENTS.md` and `.claude/skills/scaffold-integration-tests/SKILL.md` — a
  handful of three-item lists carried a comma before the final `and`/`or`, contradicting `AGENTS.md`'s own Serial
  Commas convention

#### Tooling

- `.claude/skills/generate-pr-summary`, `.claude/skills/prep-version-release`,
  `.claude/skills/update-improvement-plan-gaps`: updated to read/write archived release docs at the optional
  `documentation/history/v<major>/...` path alongside the existing flat one

---

## 🚀 Migration Guide

No code, schema or dependency changes in this release. The `documentation/history/v<major>/` grouping is opt-in —
nothing changes for a project that keeps the flat layout.

---

## 📊 Statistics

- **Total Commits:** 2
- **Files Changed:** 5
- **Insertions:** 51 lines
- **Deletions:** 18 lines
- **Net Change:** +33 lines

---

## 🧭 Design Notes

- **Document the layout as optional, not mandatory.** A brand-new project scaffolded from this template starts with
  a handful of releases at most — grouping `documentation/history/` into `v<major>/` subdirectories from day one
  would add structure the project doesn't need yet, so the convention is framed as a scaling step to adopt once the
  folder gets unwieldy, matching how `hpsc-web-springboot` itself only adopted it after accumulating eight major
  versions.
- **Keep every consumer of a path in sync in the same change.** The three skills that read or write
  `documentation/history/...` paths were updated in the same release as the `AGENTS.md` convention they implement,
  rather than left to drift.

---

## 🧪 Testing

- No automated test suite — this is a documentation-only template.
- Manual line-wrap check (100–120 characters, tables/code blocks exempt) across every changed file.

---

## 🐛 Known Issues

- `README.md`, `ARCHITECTURE.md`, `CONTRIBUTING.md` and `LICENSE.md` still don't exist in this template (carried
  over from v1.0.0).
- No `documentation/roadmap/improvement-plan.md`/`improvement-plan-tasks.md` exists yet (carried over from v1.0.0).

---

## 🔮 Future Enhancements

- Keep syncing genuinely reusable conventions back from `hpsc-web-vite`/`hpsc-web-springboot` as they evolve.
- Fill in the *(fill in)* scaffolding in `AGENTS.md` and each skill once this template is used to scaffold an
  actual project.

---

## 👥 Contributors

Leoni Lubbinge

---

## 📝 Notes

Version 1.1.0 keeps this template's conventions current with the sibling projects it was originally combined from,
without imposing new structure on projects that don't need it yet.

---

**For detailed change history, see [CHANGELOG.md](CHANGELOG.md)**

**For previous releases, see the [history folder](/documentation/history)**
