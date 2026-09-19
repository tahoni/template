---
name: prep-version-release
description: Prepare a new version release — RELEASE_NOTES.md, CHANGELOG.md, HISTORY.md, reverse-synced docs and a draft release PR description — following AGENTS.md's Release Checklist. Use whenever the user is preparing/cutting a release PR or asks to draft release documentation for a version.
user-invocable: true
allowed-tools:
  - Bash(git log:*)
  - Bash(git --no-pager log:*)
  - Bash(git diff:*)
  - Bash(git --no-pager diff:*)
  - Bash(git branch:*)
  - Bash(git status:*)
  - Bash(git merge-base:*)
  - Read
  - Edit
  - Write
---

# Prepare Version Release

The version to prepare a release for is passed as `args` (e.g. `7.2.0`) — if not supplied, try the project's manifest
file's current version field first (gathered below) before asking the user, since a release branch typically already
has it bumped. The rest of this skill refers to the resolved value as `$VERSION`.

*(fill in)* Add any stack-specific `allowed-tools` entries this skill needs beyond git/Read/Edit/Write (e.g. a
lint/build/test command pattern) once the project's tooling is known.

## 🔍 Gather current state

Before drafting, run these yourself and read their output:

1. `git branch --show-current`
2. The project's manifest file's current version field. *(fill in)* — e.g. `package.json`'s `version`, `pom.xml`'s
   `<version>`.
3. `git --no-pager diff --stat main...HEAD` (changes relative to `main`)
4. `git log main..HEAD --oneline` (commit log relative to `main`)
5. Read `CHANGELOG.md`'s current `[Unreleased]` section.
6. Read `AGENTS.md` in full for conventions.

## 🚀 Instructions

Read and strictly follow **all conventions defined in AGENTS.md** (loaded above) — in particular its **Release
Checklist**, **Documentation Conventions**, **Git Workflow** (Branching Model), **Evergreen Documentation** (reverse
sync rule), **Build & Run Commands** and **Architecture** sections for accurate technical detail (build/test commands,
directory/package layout) when writing `RELEASE_NOTES.md`/the PR description. Treat it as the single source of truth;
do not reinterpret or contradict its rules. Follow the Release Checklist steps **in order** — the version number and
date must be final before anything downstream references them.

Steps (mirroring AGENTS.md's Release Checklist):

1. **Confirm the diff against `main`** (gathered above) covers everything that changed for this release — re-run
   `git log main..HEAD` / `git diff --stat main...HEAD` yourself if the branch has moved on since this skill started.
   *(fill in, if applicable)* If the project has a per-change freshness/derived-artefact rule analogous to a sitemap
   `dateUpdated` field, verify it's up to date across the diff and regenerate any derived file before continuing.
2. **Run the `update-improvement-plan-gaps` skill, then the `sync-improvement-plan-gaps` skill, in that order.** The
   first does a full codebase sweep for brand-new gaps against `documentation/roadmap/improvement-plan.md`/
   `improvement-plan-tasks.md`; the second then checks whether this branch's own diff has closed or progressed any of
   the gaps already tracked there (its own diff-gathering step needs the plan to already reflect anything new the
   first skill just found). Neither commits on its own — review their draft edits with the user before continuing.
   This satisfies AGENTS.md's Release Checklist step of checking the roadmap docs before starting version-specific
   work.
3. **Bump the version.** If the manifest file's version field doesn't already equal `$VERSION`, update it now, along
   with any secondary place that mirrors it *(fill in, if applicable)* — e.g. an API definition's declared version, an
   app metadata constant. Search the codebase for other literal occurrences of the previous version string to catch
   anything not covered by AGENTS.md's Tech Stack/Architecture sections.
4. **Run the `sync-unreleased-changes` skill before touching CHANGELOG.md.** Diff it against whichever base branch
   AGENTS.md's Branching Model says this release branch was cut from and ships against (`main` if the release branch
   diffs against `main` to show everything it ships; `develop` if that's this project's release-cut base) — never skip
   this even if `[Unreleased]` looks complete: it cross-checks every commit and any uncommitted diff against the
   actual `[Unreleased]` entries, fills in anything missing, flags drifted entries and consolidates duplicate `Area`
   sub-headers. The next step renames `[Unreleased]` wholesale, so it must be fully accurate first. If it flags any
   entries as drifted, resolve those with the user before continuing — don't fold a flagged entry into the new version
   section unresolved.
5. **Promote `[Unreleased]` to a dated version entry.** Rename it `[$VERSION] - YYYY-MM-DD` (its entries now synced in
   the previous step), matching this project's existing CHANGELOG.md heading depth, keeping only the categories that
   apply (`➕ Added`, `🔄 Changed`, `🐛 Fixed`, `⚠️ Deprecated`, `🗑️ Removed`, `🔐 Security`) and their `Area`
   subheadings. Update the Table of Contents and move the "← Current" marker to the new version, then start a fresh,
   fully-empty `[Unreleased]` section above it (all category headings, empty).
6. **Replace `RELEASE_NOTES.md`.** Unlike `CHANGELOG.md`, this file holds only the *current* release. Follow the
   established section order: Theme → Key Highlights → What's New (Added/Changed/Fixed/Removed) → Migration Guide →
   Statistics → Design Notes → Testing → Known Issues → Future Enhancements → Contributors → Notes. Cover
   **everything** that changed for this version, not just the most recent commit. For the **Contributors** section,
   list every unique commit author on the release branch since it diverged from `main` — `git log main..HEAD
   --format='%an'` (or the equivalent GitHub "Contributors" view for the release's PRs), deduplicated — rather than a
   generic placeholder like "Development Team", and include every account found; bots (e.g. `dependabot[bot]`,
   `ImgBotApp`) included. Replace the previous version's content outright rather than appending to it.
7. **Verify links and dates.** Confirm the `v$VERSION` tag slug and the `YYYY-MM-DD` date match between
   `CHANGELOG.md` and `RELEASE_NOTES.md`.
8. **Extend `HISTORY.md`.** Add a Historical Timeline entry, a Phase and a Milestone for `$VERSION`, at the same
   narrative depth and style as the existing entries, placed at the top (immediately below the Overview section) to
   keep reverse chronological order. If the release is significant enough to have shifted the project's trajectory,
   also thread it through the other version-by-version sections (Architectural Evolution, Feature Timeline, Key
   Learnings, Future Roadmap, Conclusion/footer), using the immediately preceding version's treatment as the template.
   Then check whether `documentation/roadmap/improvement-plan.md`'s Goals & Constraints table needs a matching
   update — it's synthesised partly from `HISTORY.md`'s Future Roadmap Implications sections, so a change here can
   leave that table stale.
9. **Update `CONTRIBUTING.md`** only if this version's changes affect developer setup, environment variables,
   development scripts, git workflow or testing conventions documented there.
10. **Verify `ARCHITECTURE.md`'s Project Structure tree against disk.** Per-change Directory Tree Maintenance still
    lets drift slip through, so treat every release as a backstop: cross-check the tree against the actual repository
    structure and correct any directory that's missing, renamed or gone stale, including tracked tooling directories
    (`.claude/`, `.github/`) — not just the source tree.
11. **Apply the reverse sync rule**: check whether any of this version's changes are relevant to `README.md` (goal,
    tech stack, project structure, quick start) or `ARCHITECTURE.md` (system design, layering, data flows) — and any
    other evergreen doc this project maintains *(fill in, if applicable)* — and update those files accordingly,
    keeping them all release-agnostic (no version numbers or counts that drift, per AGENTS.md's Evergreen
    Documentation rules).
12. **Archive `RELEASE_NOTES.md`.** Once finalised, copy it byte-for-byte (no edits, no trimming) to
    `documentation/history/RELEASE_NOTES_v$VERSION.md`.
13. **Write `documentation/history/PR_DESCRIPTION_v$VERSION.md`** — the body text for the release pull request. Keep
    it small — a PR body, not a second `RELEASE_NOTES.md`: a few bullets per section, high-level only. Structure:
    - `## 🎯 Summary` — two to four bullets on what the release is and why
    - `## 📦 Key Changes` — condensed from the CHANGELOG entry's categories (Added/Changed/Fixed/Removed), high-level
      rather than exhaustive
    - `## 🧪 Test Plan` — checklist of what was verified (build, lint, tests, manual checks — *(fill in)* the actual
      commands)
    - `## 🔗 Related Documentation` — links to `RELEASE_NOTES.md`, `CHANGELOG.md`, `HISTORY.md`
    - End the file with the standard Claude Code attribution footer (a blank line, then
      `🤖 Generated with [Claude Code](https://claude.com/claude-code)`) — this is a PR description drafted by Claude
      Code and should be marked as such, same as any other PR description it opens.

Commit these in logical chunks per AGENTS.md's Git Workflow — the version bump, the CHANGELOG/HISTORY/RELEASE_NOTES
documentation, any evergreen-doc reverse-sync updates and the PR description are separate concerns unless trivially
small. Do not run `git commit`, `git push` or open the PR yourself — draft the files and stop for review.

## 📤 Output

Once all files above are written, tell the user the release branch (`release/v$VERSION`) is ready to open as a PR
against whichever branch AGENTS.md's Branching Model designates as the release-cut target, using
`documentation/history/PR_DESCRIPTION_v$VERSION.md` as the PR body. If that target isn't `main` directly, remind them
a second promotion PR is still needed to actually ship the release — tag the resulting commit on `main` as
`v$VERSION` *(fill in, if applicable)* — confirm this matches the tag format actually used in this project's existing
`CHANGELOG.md`/`RELEASE_NOTES.md` links, since a project may have changed its tag format at some point in its
history.

Remind the user to run this project's lint/build/test commands (per AGENTS.md's Build & Run Commands) before
finishing, and confirm no version-specific info leaked into `README.md`/`ARCHITECTURE.md` or any other evergreen doc.
