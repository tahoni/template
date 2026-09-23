# PR: Release v1.1.0

## 🎯 Summary

- Syncs two conventions from the sibling `hpsc-web-springboot` project, which had evolved past the point this
  template was last combined from it.
- Documents an optional per-major-version `documentation/history/v<major>/` subdirectory grouping and a companion
  `HISTORY.md`/`EVOLUTION_OVERVIEW.md` split, for projects whose release archive grows large.
- Formalises an optional three-tier layered test architecture for layered, interface-based backends.

## 📦 Key Changes

- `AGENTS.md`: Documentation File Map and Release Checklist document the optional `documentation/history/v<major>/`
  grouping and `EVOLUTION_OVERVIEW.md` split.
- `AGENTS.md`: Test Conventions section formalises the optional three-tier layered test architecture.
- `generate-pr-summary`, `prep-version-release`, `update-improvement-plan-gaps` skills updated to read/write the
  optional `v<major>/` path.
- Serial-comma violations fixed in `AGENTS.md` and `scaffold-integration-tests/SKILL.md`.

## 🧪 Test Plan

- [x] Manual review confirming `AGENTS.md` and the three updated skills describe the same optional path
  consistently.
- [x] Line-wrap check (100–120 characters, tables/code blocks exempt) across all changed files.
- [ ] No automated build/lint/test — this template has no source code.

## 🔗 Related Documentation

- [RELEASE_NOTES.md](/documentation/history/v1.1/RELEASE_NOTES_v1.1.0.md)
- [CHANGELOG.md](/CHANGELOG.md)
- [HISTORY.md](/HISTORY.md)

🤖 Generated with [Claude Code](https://claude.com/claude-code)
