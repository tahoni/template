# PR: Release v1.2.0

## 🎯 Summary

- Adds fill-in-template scaffolds for every documentation file `AGENTS.md`'s Documentation File Map names, so a new
  project gets a starting point for each one instead of only the rules for writing it.
- Moves this template's own `README.md`/`CHANGELOG.md`/`HISTORY.md`/`RELEASE_NOTES.md` into
  `documentation/current/`, which frees the root names for the scaffolds, and backfills its release history for
  v1.0.0 and v1.1.0.
- Makes the `HISTORY.md` → `documentation/history/EVOLUTION_OVERVIEW.md` split mandatory from the first release.

## 📦 Key Changes

- Root-level scaffolds: `README.md`, `ARCHITECTURE.md`, `CONTRIBUTING.md`, `HISTORY.md`, `CHANGELOG.md`,
  `RELEASE_NOTES.md` and an MIT `LICENSE.md` with placeholders.
- Optional stack-specific scaffolds: `UI.md`, `PACKAGES.md` and `HELP.md`.
- Template's own docs moved to `documentation/current/`, with the release archive grouped into
  `documentation/history/v1/`.
- `AGENTS.md` Documentation File Map/Release Checklist and the `prep-version-release` skill updated for the
  always-split `EVOLUTION_OVERVIEW.md`.

## 🧪 Test Plan

- [x] Line-wrap check (100–120 characters, tables/code blocks exempt) across all changed files.
- [x] Manual review confirming internal links resolve after the `documentation/current/` move.
- [x] `RELEASE_NOTES_v1.2.0.md` archive is a byte-for-byte copy of `documentation/current/RELEASE_NOTES.md`.
- [ ] No automated build/lint/test — this template has no source code.

## 🔗 Related Documentation

- [RELEASE_NOTES.md](/documentation/history/v1/RELEASE_NOTES_v1.2.0.md)
- [CHANGELOG.md](/documentation/current/CHANGELOG.md)
- [HISTORY.md](/documentation/current/HISTORY.md)

🤖 Generated with [Claude Code](https://claude.com/claude-code)
