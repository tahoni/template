# AGENTS.md

Conventions for any AI coding agent working in this repository — project overview, tech stack, build/run commands,
environment variables, architecture, code quality & CI, documentation conventions, roadmap planning, Claude Code
skills, testing, git workflow and the release checklist all live here. [`CLAUDE.md`](CLAUDE.md) is a thin pointer to
this file, kept only because Claude Code specifically looks for a file by that name. Some content (documentation
conventions, icon reuse) is intentionally restated in both this file and the per-file docs it governs, since not
every agent tool reads `AGENTS.md`.

This file is a **template**. Every section below is either directly reusable as-is (marked *(reusable as-is)*) or a
scaffold to fill in for the specific project (marked *(fill in)*) — replace the bracketed guidance with the
project's own details and delete these template notes once done.

## Table of Contents

- [📖 Project Overview](#-project-overview)
- [⚙️ Tech Stack](#-tech-stack)
- [🚀 Build & Run Commands](#-build--run-commands)
- [🔧 Environment Variables](#-environment-variables)
- [🏛️ Architecture](#-architecture)
- [🔬 Code Quality & CI](#-code-quality--ci)
- [📚 Documentation Conventions](#-documentation-conventions)
- [🗺️ Documentation File Map](#-documentation-file-map)
- [🛤️ Roadmap Planning](#-roadmap-planning)
- [🧩 Claude Code Skills](#-claude-code-skills)
- [🧪 Test Conventions](#-test-conventions)
- [📁 Directory Tree Maintenance](#-directory-tree-maintenance)
- [🔀 Git Workflow](#-git-workflow)
- [🚢 Release Checklist](#-release-checklist)
- [🌲 Evergreen Documentation](#-evergreen-documentation-readmemd--architecturemd)

---

## 📖 Project Overview

*(fill in)* One short paragraph: what the project is, who it's for, and its shape at a glance — e.g. "is a
[frontend/backend/library/CLI] for [domain]". State plainly whether this repository is standalone (no
backend/frontend counterpart) or one half of a paired frontend/backend system, and link the other half if so.

- **Entry point:** *(fill in)* — e.g. dev server URL, listening port, or CLI command.
- **API docs / other key URL:** *(fill in, if applicable)* — e.g. Swagger UI, Storybook, generated docs.

---

## ⚙️ Tech Stack

*(fill in)* A bullet list of the language, framework, build tool, persistence layer, testing stack, linting and any
notable libraries — one line each, naming the tool, not the version:

```
- **Language:**
- **Framework:**
- **Build tool:**
- **Testing:**
- **Linting / static analysis:**
- **API documentation:**
```

Exact pinned versions are not listed here — they drift with every dependency bump. Check the project's manifest
file (`package.json`, `pom.xml`, etc.) for the versions currently in use. *(reusable as-is)*

---

## 🚀 Build & Run Commands

*(fill in)* The minimal command set an agent needs to install, run and test the project, e.g.:

```bash
# Install dependencies

# Run the dev server / application

# Run the test suite

# Build for production / package
```

See `README.md`'s Available Scripts / Getting Started section for the complete command list. *(reusable as-is)*

---

## 🔧 Environment Variables

*(fill in, if applicable)* A table of required environment variables, where they're consumed and what they're for:

| Variable | Used in | Purpose |
|----------|---------|---------|
|          |         |         |

Keep a secret-free `.env.example` (or equivalent) as the copy-to-`.env.local` starting point; document its variable
naming convention here rather than duplicating every value. *(reusable as-is)*

---

## 🏛️ Architecture

*(fill in)* A short flow diagram plus a directory/package table orient an agent quickly; put the full design in
`ARCHITECTURE.md` and summarise it here. For example, a layered backend might read:

```
Request
    → Controller / Handler
    → Service        (business logic)
    → Repository      (persistence)
    → Database
```

...while a component-based frontend might read:

```
Route
    → Feature page
    → Feature content
    → Common components / layouts
```

### Key directories / packages

*(fill in)* One row per top-level source directory, describing its role generically — never enumerating the
individual files or classes inside (see [📁 Directory Tree Maintenance](#-directory-tree-maintenance)).

### Code style

*(fill in, if applicable)* Any structural conventions specific to the language/paradigm in use — for example:

- **Member ordering** (OOP languages): constructors first, then public methods, then protected, then private helpers
  last (private helpers always sit at the very end, below every protected method, regardless of declaration order).
  Within each visibility group, keep the existing relative order rather than alphabetising, except where a stricter
  test-class convention overrides this (see [🧪 Test Conventions](#-test-conventions)).
- **API/REST conventions** (if the project exposes an HTTP API): URL paths name the resource, not the action (plural
  nouns for collections, a path variable for a single resource); never encode the HTTP verb into the path; handler
  methods are named `<action><Resource>` using the verb each HTTP method typically maps to.
- **Component/module folder shape** (component-based UIs): each non-trivial component gets its own folder
  (component file, scoped styles, subcomponents, local constants, barrel export).

---

## 🔬 Code Quality & CI

*(fill in)* Name each automated gate and what triggers it — for example:

- **Static analysis / security scanning** (e.g. CodeQL): what it runs on and how often.
- **Linting**: which config, and whether it must report zero warnings (not just zero errors).
- **Build workflow**: which commands run on push/PR (lint, build, test) and what branches/gates it protects.
- **Dependency audit**: how often dependencies are reviewed (`npm outdated`/`npm audit`, `mvn versions:display-dependency-updates`,
  etc.), whether it's advisory-only or blocking, and which dependencies sit on a security-sensitive boundary
  (user-submitted content, auth, bot protection) and deserve extra scrutiny — read the changelog before upgrading
  those, not just accepting an automatic bump.

---

## 📚 Documentation Conventions

### British English

All documentation prose and code comments use British English spelling (e.g. "licence", "organisation", "colour",
"initialise"), not American English.

**Exceptions:**

- Standard legal or licence boilerplate. The `LICENSE.md` file itself (name and content) is a fixed legal term in
  American English and must not be altered; every other doc that names or links to it (headings, tables, ToC entries)
  spells it "Licence" instead, per the British English convention above.
- Third-party product, library and API names.
- Code identifiers (component, function, class and variable names) — these follow the codebase's existing naming
  conventions, not spelling conventions, unless the project's own style explicitly extends British spelling to
  identifiers too.

### Serial commas

Lists of three or more items don't take a comma before the final `and`/`or` (e.g. "news, events and venues", not
"news, events, and venues") — consistent with the British English convention above. This doesn't apply to a comma
joining two independent clauses (e.g. "the build passed, and the release was tagged"), only to the last item of a
list.

### API documentation comments (TSDoc / Javadoc / docstrings / etc.)

- Use British English conventions (spelling, grammar, punctuation), consistent with the rest of this project's
  documentation — not American English.
- Follow whatever syntax-checking lint rule the toolchain provides (e.g. `eslint-plugin-tsdoc`'s `tsdoc/syntax`) so
  doc comments stay valid, not just close enough for the tool in use.
- Document exported/public members with a summary line and the parameter/return/throws tags the language supports,
  where the signature isn't self-explanatory from its types.
- Don't restate what the type system already makes obvious (e.g. don't write "the name" for a `name: string`
  parameter) — reserve prose for behaviour, side effects and non-obvious constraints.
- Include a short usage example on non-trivial utility functions/classes and non-obvious constructors.
- Don't duplicate an interface/abstract method's doc comment on its implementation unless the implementation has
  behaviour the contract doesn't already describe.

### Contributors

When documentation credits contributors or authors (e.g. `README.md`'s Author section, a release PR description),
source the list from actual git/GitHub history — never assume or guess who contributed. Run
`git log --format='%an <%ae>' | sort -u` (or check the repository's GitHub Contributors view) and include every
account found, bots (e.g. `dependabot[bot]`, `ImgBotApp`) included.

### Standard structure

Every documentation file in this repository follows the same shape:

- An `H1` title, followed by a short introductory sentence or two.
- A Table of Contents for any document with more than roughly four sections.
- `##` sections, separated by a `---` horizontal rule between major sections.
- GFM tables for structured or tabular information (technology lists, directory overviews, file maps).
- Fenced code blocks for directory trees and flow diagrams.

### Line wrapping

Wrap prose lines in Markdown files to between 100 and 120 characters. Tables are exempt — keep each row on a single
line regardless of length, since wrapping breaks GFM table syntax; the same applies to fenced code blocks, directory
trees and diagrams, which keep their own natural line lengths.

### Icons in headings

Every heading listed in a Table of Contents is prefixed with an emoji, and its ToC entry uses the same emoji. Reuse
an icon already established for a concept rather than inventing a new one; only pick a new emoji when introducing a
genuinely new concept. Core icons this template already establishes, applicable to any project:

| Icon | Concept                                             |
|------|-----------------------------------------------------|
| 📖   | Introduction / overview                             |
| 🔗   | Repository / links                                  |
| ⚙️   | Technology / configuration                          |
| 🚀   | Instructions / getting started                      |
| 🔧   | Installation / setup / technical change             |
| 📋   | Prerequisites / policy                              |
| 📁   | Project / directory structure                       |
| 🎯   | Core concepts / theme overview                      |
| ✍️   | Content strategy / documentation conventions        |
| 🛠️   | Development guidelines                              |
| 👤   | Author / changes by                                 |
| 🗺️   | Documentation file map                              |
| 🛤️   | Roadmap                                             |
| 📚   | Documentation / key learnings                       |
| 🏛️   | Architecture                                        |
| 🧪   | Testing                                             |
| 🔀   | Git workflow                                        |
| 🚢   | Release process                                     |
| 🌲   | Evergreen documentation                             |
| 🔍   | Current state / inspection                          |
| 🔬   | CI/CD & quality gates                               |
| ☑️   | Checklist                                           |
| 💬   | Support                                             |
| ✨   | Features / enhancements                             |
| 🧾   | Change log / release notes                          |
| 🐛   | Bug fixes / known issues                            |
| ➕   | Added items                                         |
| 🔄   | Changed items                                       |
| ⚠️   | Deprecated items                                    |
| 🗑️   | Removed items                                       |
| 🔐   | Security                                            |
| 🤝   | Contributing                                        |
| 📅   | Historical timeline / dates                         |
| 💡   | Philosophy / insight                                |
| 🎓   | Conclusion / retrospective                          |
| 📦   | Dependencies / what's new                           |
| ⭐   | Key highlights                                      |
| 📊   | Statistics                                          |
| 🔮   | Future enhancements                                 |
| 👥   | Contributors                                        |
| 📝   | Notes                                               |
| 🧩   | Tooling / automation                                |
| 📜   | Licence and documentation                           |
| ♻️   | General code improvements                           |
| 💰   | Funding / sponsorship                               |
| 📤   | Output                                              |
| 👍   | Recommendation / best practices                     |
| ✅   | Quality attributes / completed (roadmap gap status) |
| 🟡   | Partially completed (roadmap gap status)            |
| ⚪   | Open / not started (roadmap gap status)             |
| 🧭   | Design notes                                        |
| 🌳   | Decision tree / quick reference                     |
| 🏆   | Most popular / prevailing convention                |
| 🗝️   | Key principles                                      |
| ⏭️    | Next / upcoming                                     |
| ⏳   | Later / pending                                     |
| 🔁   | Ongoing / recurring                                 |
| 🏷️   | Naming conventions                                  |
| ⚖️   | Comparison / trade-offs                             |
| 🤔   | Reasoning                                           |

Two optional extension sets exist for common project shapes — pick the one matching this project's stack (or both,
for a paired frontend/backend system) so that sibling repos of the same shape stay visually consistent, and keep the
other reserved rather than repurposing its icons for an unrelated concept here:

| Icon | Reserved for (backend / API service) |
|------|--------------------------------------|
| ⚡   | Service layer                        |
| 📈   | Request-response flow                |
| 📥   | Inbound / import flow                |
| 🔓   | Optional / relaxed constraint        |
| 🔢   | Numbering / sequence                 |
| 🗄️   | Database / persistence               |
| 🛡️   | Robustness / validation hardening    |
| 🌐   | Presentation / API layer             |
| 🏗️   | Layered architecture                 |
| 🧬   | Data model / DTOs                    |

| Icon | Reserved for (component-based frontend) |
|------|-----------------------------------------|
| 🧰   | Available scripts / tooling             |
| 🛣️   | Routing / navigation                    |
| 🗂️   | Feature-based organisation              |
| 🎨   | Styling and theming / design            |
| 📐   | Layout structure                        |
| 🔝   | Header                                  |
| 📄   | Body / page content                     |
| ⬇️   | Footer                                  |
| 📱   | Responsive design                       |
| 💻   | Technical implementation                |
| 🖥️   | User interface                          |
| 🌊   | Global scope / cascading styles         |
| 🧵   | Shared / cross-feature infrastructure   |
| 🧱   | Component/layout folder shape           |

---

## 🗺️ Documentation File Map

Root-level documentation, and the goal of each file (see `README.md`'s own Documentation section — `README.md` is
the canonical version if the two ever drift). Of these, `AGENTS.md` is the ultimate source of truth for this
project's conventions — every other file's workflow/convention guidance (`CONTRIBUTING.md` included) points back to
it rather than restating it, so it's the one to update first when a convention changes:

| File               | Purpose                                                                        |
|--------------------|--------------------------------------------------------------------------------|
| `README.md`        | Project overview, setup and links to the rest of the documentation             |
| `ARCHITECTURE.md`  | Detailed architectural design, directory/package structure and core concepts   |
| `CLAUDE.md`        | Thin pointer to `AGENTS.md`, kept for tools that specifically read `CLAUDE.md` |
| `AGENTS.md`        | Cross-tool agent conventions — the full guidance (this file)                   |
| `CONTRIBUTING.md`  | Contributor-facing setup, git workflow and pull request checklist              |
| `CHANGELOG.md`     | Notable changes per released version, in Keep a Changelog format               |
| `HISTORY.md`       | Narrative history of the project's evolution across all versions               |
| `RELEASE_NOTES.md` | Detailed release notes for the current/latest version only                     |
| `LICENSE.md`       | Project licence                                                                |

*(fill in, if applicable)* Add stack-specific docs the project needs — e.g. `UI.md` (frontend layout/navigation),
`PACKAGES.md` (dependency/funding manifest), `HELP.md` (framework-generated reference links).

These documentation-only folders supplement it:

- **`documentation/history/`** holds one of each of the following files per released version, archived once the
  release is finalised:

  | File                       | Purpose                                                    |
  |----------------------------|------------------------------------------------------------|
  | `RELEASE_NOTES_vX.Y.Z.md`  | Archived snapshot of `RELEASE_NOTES.md` at release time    |
  | `PR_DESCRIPTION_vX.Y.Z.md` | The release pull request's body, archived for that version |

  *(fill in, if applicable)* Once this folder accumulates enough releases to make browsing it unwieldy, group its
  files into `v<major>/` subdirectories by major version (e.g. `documentation/history/v8/RELEASE_NOTES_v8.6.0.md`),
  creating a new `v<major>/` folder the first time a release starts a new major version — see the Release Checklist
  below. Similarly, if `HISTORY.md`'s own narrative grows too large, a phase-by-phase section of it can be split out
  into a standing companion file living directly in `documentation/history/` (not per-version), e.g.
  `documentation/history/EVOLUTION_OVERVIEW.md`.

- **`documentation/roadmap/`** holds in-progress planning documents that sit outside the standard documentation set
  above — see [🛤️ Roadmap Planning](#-roadmap-planning) below for the file structure and conventions.
- **`documentation/recommendations/`** holds the fuller rationale and current-codebase examples behind conventions
  this file states only as a condensed rule elsewhere.
- **`documentation/archive/ARCHIVE.md`** is the legacy release archive covering any pre-semantic-versioning /
  pre-`CHANGELOG.md` era of the project. It is a historical record only and is not maintained going forward.

---

## 🛤️ Roadmap Planning

Unlike the folders above, `documentation/roadmap/` isn't reference material — it's the project's active improvement
backlog, kept separate from the standard documentation files:

- **`improvement-plan.md`** — opens with a Goals & Constraints table synthesised from the project's own docs and
  configuration, then a "🔍 Gaps & Improvement Opportunities" section grouping numbered `#### N. <Title>` gap
  sections into three status subsections — ✅ Completed, 🟡 Partially Completed, ⚪ Open — each with Evidence,
  Why it matters and a Proposed improvement, gaining an Outcome or Progress paragraph once work against it lands.
  That's followed by a Now/Next/Later/Ongoing Roadmap table (forward-looking priority, a separate concern from
  completion status) and a Success Criteria list.
- **`improvement-plan-tasks.md`** — mirrors the same three status subsections, breaking each gap into checkboxes,
  organised by the plan's Now/Next/Later/Ongoing phasing, with each item/block naming its originating gap number.

A gap's number is assigned once and never reused or resequenced, so it stays stable even as the gap moves between
sections. A gap moves to 🟡 Partially Completed once it has a documented Progress note (or, in
`improvement-plan-tasks.md`, at least one checked item) but hasn't reached a final Outcome, and to ✅ Completed once
it has (its header gains a "— ✅ Closed in vX.Y.Z" suffix, or "— ✅ Closed as not applicable in vX.Y.Z" if it was
resolved by removing the thing rather than delivering it). Never delete or renumber a gap or delete a checked task
line when moving it between sections — only relocate the whole block.

Unlike `README.md`/`ARCHITECTURE.md`, `improvement-plan.md` is explicitly **not evergreen** — it's a point-in-time
reading of the project, revisited only when a gap closes, progresses or a new one is identified; the original
analysis is never deleted or rewritten. Check both files before assuming a gap (missing CI pipeline, no tests, no
`CONTRIBUTING.md`) is unintentional; it may already be tracked there. Checking this file is also the first step of
the [🚢 Release Checklist](#-release-checklist) below.

---

## 🧩 Claude Code Skills

`.claude/skills/` holds project-specific Claude Code skills that turn this file's conventions into ready-to-invoke
workflows, available to any Claude Code session in this repository. The following skill names are common to any
project built from this template — each encodes a workflow described elsewhere in this file, so an agent doesn't
have to reconstruct it from scratch each time:

| Skill                          | Purpose                                                                                                                 |
|--------------------------------|-------------------------------------------------------------------------------------------------------------------------|
| `generate-commit-message`      | Draft a commit message and matching `CHANGELOG.md` entry for the current working tree changes                           |
| `generate-pr-summary`          | Condense a version's `PR_DESCRIPTION.md`/`RELEASE_NOTES.md` into a short PR summary                                     |
| `prep-version-release`         | Prepare a new version release — release notes, changelog, history, docs and a draft PR, per the Release Checklist below |
| `scaffold-integration-tests`   | Scaffold integration tests for a service/feature, per the Test Conventions below                                        |
| `scaffold-unit-tests`          | Scaffold unit tests for a component/class/function/helper, per the Test Conventions below                               |
| `sync-improvement-plan-gaps`   | Check the current branch's changes against `improvement-plan.md`'s tracked gaps and mark any closed/progressed          |
| `sync-unreleased-changes`      | Audit the current branch's diff and ensure every notable change is reflected in `CHANGELOG.md`'s Unreleased section     |
| `update-improvement-plan-gaps` | Audit the codebase against `improvement-plan.md`/`improvement-plan-tasks.md` and record any newly identified gaps       |

*(fill in, if applicable)* Add project-specific skills alongside these (e.g. a stack-specific scaffolding or
migration skill).

Every skill reads this file in full before acting and treats it as the single source of truth for the conventions it
automates — a skill's own instructions must never drift from what's documented here; fix this file first, then
update the skill to match. AI coding agents without Claude Code's skill support should follow this file's
conventions directly rather than relying on the skills existing.

---

## 🧪 Test Conventions

*(fill in)* Name the test framework(s), how to run them (watch mode vs. single CI run) and where coverage reporting
lives. The following structural rules apply regardless of language:

- Co-locate test files next to the file under test, or mirror the source tree under a dedicated test root — pick
  whichever convention the language's tooling favours and stay consistent.
- Prefer testing behaviour and observable output over implementation details; avoid brittle assertions on
  private/internal state or over-specified mock-call-count checks.
- Don't write tests whose sole purpose is verifying language/framework/ORM-generated trivial behaviour — e.g. the
  type system, a generated getter/setter, or a trivial pass-through constructor with no custom logic. Using such
  generated members incidentally to build fixtures or assert real behaviour is fine; only test them directly when
  they're handwritten or contain custom logic.
- Follow an Arrange-Act-Assert structure, marking each phase present with a comment (`// Arrange`, `// Act`,
  `// Assert`) — omit a phase's comment only when that phase doesn't apply. A test that only verifies a thrown
  exception can combine the last two into a single `// Act & Assert` comment.
- **Group and order tests by the member under test**, preceding each group with a one-line comment naming it.
  Order the groups: constructors first; then public members before protected/internal ones; within each visibility,
  alphabetically by name (for overloads, by parameter count then parameter type).
- **Move private helper/fixture methods to the end of the test file**, under a `// Helpers` comment, so the tests
  themselves stay at the top, uninterrupted by setup code.
- *(fill in, if applicable)* **For a layered, interface-based architecture** (e.g. a service backed by an interface
  and its own implementation class), split coverage into up to three tiers rather than one do-everything test class:
  1. A unit test of the interface's own public contract, exercised **through the interface type**, with every
     dependency mocked.
  2. A separate unit test for the implementation class's own protected/private helper methods that aren't declared
     on the interface, likewise fully mocked.
  3. An integration test exercising the same public contract end-to-end through the real, framework-wired
     implementation, with no mocks.

  Not every layer needs all three tiers — apply this split only where the interface/impl divide carries genuinely
  independent logic worth testing separately. See the `scaffold-unit-tests`/`scaffold-integration-tests` skills
  above for the detailed per-tier scaffolding rules.

---

## 📁 Directory Tree Maintenance

- Whenever a root-level directory (or a top-level source directory) is added or removed, `ARCHITECTURE.md`'s Project
  Structure tree must be updated in the same change.
- Directories covered by `.gitignore` (build output, IDE state, logs, dependency caches) must never appear in that
  tree.
- Tracked tooling directories — `.claude/` and `.github/` — do belong in the tree, even though they sit alongside
  gitignored directories at the repository root: they hold version-controlled configuration (Claude Code skills,
  GitHub Actions workflows) rather than local machine state.
- Directory/package comments in the tree describe purpose generically and must never enumerate the individual
  files or classes inside — those are added, renamed and removed far more often than the directories that hold
  them, so a listed name goes stale quickly while the generic description keeps the tree evergreen.

---

## 🔀 Git Workflow

### Branching Model (GitFlow)

This repository follows the [GitFlow](https://nvie.com/posts/a-successful-git-branching-model/) branching model:

- **`develop`** is the current development branch — all day-to-day work lands here first.
- **`main`** is the production branch. It is only ever updated by promoting `develop` after a `release/vX.Y.Z`
  branch has merged into it, or directly from a `hotfix/*` branch — never any other source.
- **`feature/<short-description>`** — day-to-day feature and bug-fix work. Branch from, and PR back into, `develop`.
- **`release/vX.Y.Z`** branches are cut from `develop` once it's ready to ship — they carry the release-prep changes
  (version bump, `CHANGELOG.md`/`RELEASE_NOTES.md`, etc.; see the Release Checklist below) and are opened as a PR
  against `develop`. Once that merges, a second PR promotes `develop` into `main`. **Diff a `release/vX.Y.Z` branch
  against `main`, not `develop`, to see everything it actually ships** — a diff against `develop` only shows the
  branch's own release-prep commits, since the release's feature work already landed there via earlier `feature/*`
  PRs. This is independent of where the branch's PR is opened: the PR still targets `develop`, as above.
- **`hotfix/<short-description>`** — urgent fixes for a defect already in production. Branch from, and PR directly
  into, `main`, bypassing `develop` and any in-progress `release/vX.Y.Z` branch so the fix ships immediately. Also,
  merge/PR the same fix into `develop` so it isn't lost when the next release is cut.

**All branches are committed to `develop` first, never `main`.** `hotfix/*` is the sole, deliberate exception, and
even then the same fix still lands on `develop` immediately afterwards (see Merging below). Every other branch —
`feature/*` and `release/*` included — must never open a PR directly against `main`.

### Merging

- **`feature/*` → `develop`:** once the PR is approved and CI passes, merge with a standard merge commit (matching
  this repo's existing history — no squashing or rebasing) and delete the branch afterwards.
- **`hotfix/*` → `main` and `develop`:** merge the PR into `main` first so the fix ships immediately. Then open a
  second PR carrying the same commit(s) from the `hotfix/*` branch into `develop`, referencing the original `main`
  PR in its description — only delete the branch once both merges have landed, so the fix isn't lost when the next
  `release/vX.Y.Z` branch is cut.
- **`release/vX.Y.Z` → `develop`:** merge once the Release Checklist below is complete and all tests pass, with a
  standard merge commit and delete the branch afterwards.
- **`develop` → `main`:** immediately after, open a second PR promoting `develop` into `main` and merge it; tag the
  resulting commit on `main` as `vX.Y.Z`.

### Conventions

- **Commit in logical chunks.** One concern per commit — do not bundle unrelated changes (e.g. a dependency bump, a
  documentation update and a bug fix) into a single commit.
- **Track complex work with a todo list.** For multistep or non-trivial tasks, maintain a tracked todo list and keep
  it updated as work progresses, so progress stays visible and the work stays on track.
- **Update `CHANGELOG.md` in the same change.** Every notable change gets an entry under `### 🧪 [Unreleased]`, nested
  one level deeper under the matching Keep a Changelog category heading (`#### ➕ Added`, `#### 🔄 Changed`,
  `#### 🐛 Fixed`, `#### ⚠️ Deprecated`, `#### 🗑️ Removed`, `#### 🔐 Security` — only the ones that apply), and one
  level deeper again under a `##### <Area>` sub-heading grouping related entries (reuse an existing Area from the
  file's recent entries where one fits, rather than inventing a near-duplicate) — as part of the change that makes
  it, not batched into a later, separate change. Each bullet is a plain, factual description of what changed and why,
  with backticked identifiers (component, file, constant, class) — not a bold-lead-in label.
- Commit messages are plain, imperative-mood descriptions of the change (e.g. "Refactor X: remove Y, merge
  functionality into Z"); this repository does not use a Conventional Commits prefix (`feat:`, `fix:`, etc.), unless
  the project explicitly adopts one.

---

## 🚢 Release Checklist

When cutting a new version, work through these steps **in order** — the version number and date must be final
before anything downstream references them:

1. **Check `documentation/roadmap/improvement-plan.md`/`improvement-plan-tasks.md`.** Before starting any
   version-specific work, check whether this release has closed, progressed or newly revealed any of the gaps
   tracked there, and update them accordingly.
2. **Review dependencies.** Run the stack's outdated/audit tooling locally, and triage any open Dependabot (or
   equivalent) alerts. Bump patch/minor versions where it's low-risk; give dependencies on a security-sensitive
   boundary (user-submitted content, auth, bot protection) extra scrutiny and read their changelogs before upgrading.
3. **Bump the version.** Update the version field in the project's manifest (`package.json`, `pom.xml`, etc.) and any
   secondary place that mirrors it (e.g. an API definition's declared version).
4. **Verify `CHANGELOG.md`'s `### 🧪 [Unreleased]` section is complete.** Cross-check every commit and any
   uncommitted diff on the release branch against its entries first — don't assume it's already accurate just
   because entries were added along the way; fill in anything missing.
5. **Promote `### 🧪 [Unreleased]` to a dated version entry.** Rename it `### 🧾 [X.Y.Z] - YYYY-MM-DD`, keeping only
   the Keep a Changelog categories that actually have entries. Add the new version to the Table of Contents, move
   the "← Current" marker onto it, then start a fresh, fully-empty `### 🧪 [Unreleased]` section above it.
6. **Replace `RELEASE_NOTES.md`.** Unlike `CHANGELOG.md`, this file holds only the *current* release. Suggested
   section order: Theme → Key Highlights → What's New (categorised, matching the `CHANGELOG.md` entry) →
   Migration Guide → Statistics (from `git log`/`git diff --stat` against the previous release) → Design Notes →
   Testing → Known Issues → Future Enhancements → Contributors (per the Contributors convention above) → Notes.
   Cover **everything** that changed for this version, not just the most recent commit — diff the release branch
   against the previous release tag to confirm full coverage before finalising. Replace the previous version's
   content outright rather than appending to it.
7. **Verify links and dates.** Confirm the version/tag slug and the `YYYY-MM-DD` date match between `CHANGELOG.md`
   and `RELEASE_NOTES.md`.
8. **Extend `HISTORY.md`.** Add a new entry to the Historical Timeline (Theme and Key Focus bullets, at the same
   depth as existing entries, placed at the top for reverse chronological order). If the release is significant
   enough to have shifted the project's trajectory, also thread it through any other sections that track
   version-by-version state. Use how the immediately preceding version was woven into those sections as the
   template. A routine patch release may only need the Historical Timeline entry.
9. **Update `CONTRIBUTING.md`** only if this version's changes affect developer setup, environment variables,
   development scripts, git workflow or testing conventions documented there.
10. **Verify `ARCHITECTURE.md`'s Project Structure tree against disk.** Per-change Directory Tree Maintenance
    (above) still lets drift slip through, so treat every release as a backstop: cross-check the tree against the
    actual repository structure and correct any directory that's missing, renamed or gone stale, including tracked
    tooling directories (`.claude/`, `.github/`).
11. **Archive `RELEASE_NOTES.md`.** Once finalised, copy it byte-for-byte (no edits, no trimming) to
    `documentation/history/RELEASE_NOTES_vX.Y.Z.md` — or `documentation/history/v<major>/RELEASE_NOTES_vX.Y.Z.md` if
    this project has adopted the per-major-version subdirectory grouping described in the Documentation File Map
    above (`<major>` is the leading number of `X.Y.Z` before the first `.`, e.g. `7.2.0` → `v7`; create that
    `v<major>/` folder first if this is the first release of a new major version).
12. **Write `documentation/history/PR_DESCRIPTION_vX.Y.Z.md`** (same location as step 11 above). The body text for
    the release pull request. Keep it small — a PR body, not a second `RELEASE_NOTES.md`: a few bullets per section,
    high-level only. Structure:
    - `## 🎯 Summary` — two to four bullets on what the release is and why
    - `## 📦 Key Changes` — condensed from the `CHANGELOG.md` entry's categories, high-level rather than exhaustive
    - `## 🧪 Test Plan` — checklist of what was verified (build, lint, tests, manual checks)
    - `## 🔗 Related Documentation` — links to `RELEASE_NOTES.md`, `CHANGELOG.md`, `HISTORY.md`

Commit these in logical chunks per the Git Workflow rule above — the version bump, the
CHANGELOG/HISTORY/RELEASE_NOTES documentation and the archived `documentation/history/` files are separate concerns
unless trivially small.

---

## 🌲 Evergreen Documentation (README.md & ARCHITECTURE.md)

`README.md`, `ARCHITECTURE.md` and any equivalent top-level design doc describe the durable structure and purpose of
the project, not its current-version implementation details. They must:

- **Never contain references to specific versions** — neither exact version numbers nor version ranges of this
  project. Defer to the project's manifest file for the exact version currently in use and to
  `CHANGELOG.md`/`HISTORY.md` for release history.
- **Never contain counts that drift as the codebase grows** (e.g. "Eight features are implemented"). List items by
  name in a table instead, without a leading count.
- **Never carry narrative tightly coupled to the current version's implementation.** That belongs in `CHANGELOG.md`
  or `RELEASE_NOTES.md`.

**Reverse sync rule:** When generating or updating `RELEASE_NOTES.md` or `CHANGELOG.md`, check whether any of the
changes being documented are relevant to `README.md` (goal, tech stack, quick start) or `ARCHITECTURE.md` (project
structure, core concepts, build/tooling) and update those files too if so. Don't let them fall out of sync with what
the release docs describe — while still keeping them release-agnostic per the rules above.
