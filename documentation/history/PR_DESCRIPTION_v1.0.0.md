# PR: Release v1.0.0

## 🎯 Summary

- Establishes this repository as a standalone template: a framework-agnostic `AGENTS.md`, a thin `CLAUDE.md`
  pointer and eight ready-to-invoke Claude Code skills.
- Merges the framework-agnostic parts of the sibling `hpsc-web-vite` and `hpsc-web-springboot` projects' own
  `AGENTS.md`/`.claude/skills/` into a single fill-in-template usable for any project.
- Hard-codes the commit-message shape and `CHANGELOG.md` heading depth across the git-workflow skills so they stop
  hedging between two conventions and match `AGENTS.md` exactly.

## 📦 Key Changes

- Added `AGENTS.md` — project overview, tech stack, build/run commands, environment variables, architecture, code
  quality & CI, documentation conventions, documentation file map, roadmap planning, Claude Code skills, test
  conventions, directory tree maintenance, git workflow and release checklist.
- Added `CLAUDE.md`, a thin pointer to `AGENTS.md`.
- Added eight Claude Code skills under `.claude/skills/`: `generate-commit-message`, `generate-pr-summary`,
  `prep-version-release`, `scaffold-integration-tests`, `scaffold-unit-tests`, `sync-improvement-plan-gaps`,
  `sync-unreleased-changes`, `update-improvement-plan-gaps`.
- Added baseline `.gitignore`/`.aiignore` ignore patterns.

## 🧪 Test Plan

- [x] Manual review of `AGENTS.md` and every skill's Markdown for internal consistency (no contradicting conventions
  between `AGENTS.md` and the skills that automate it).
- [x] Line-wrap check (100–120 characters, tables/code blocks exempt) across all Markdown files.
- [ ] No automated build/lint/test — this template has no source code.

## 🔗 Related Documentation

- [RELEASE_NOTES.md](/documentation/history/RELEASE_NOTES_v1.0.0.md)
- [CHANGELOG.md](/CHANGELOG.md)
- [HISTORY.md](/HISTORY.md)

🤖 Generated with [Claude Code](https://claude.com/claude-code)
