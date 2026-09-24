# {{Project Name}} Improvement Plan

This document synthesises the goals and constraints stated across this repository's documentation and configuration
into a single set of prioritised improvement opportunities. Unlike [`README.md`](/README.md) and
[`ARCHITECTURE.md`](/ARCHITECTURE.md), it is not evergreen — it reflects a point-in-time reading of the project and
should be revisited whenever a major gap it names is closed or a new one is identified. *(reusable as-is)*

This file is a **template**. Every section below is either directly reusable as-is (marked *(reusable as-is)*) or a
scaffold to fill in for the specific project (marked *(fill in)*) — replace the bracketed guidance with the
project's own details and delete these template notes once done. The `update-improvement-plan-gaps` skill can do
the first full sweep for you once `AGENTS.md` and the rest of the documentation set are filled in.

## Table of Contents

- [🎯 Purpose & Scope](#-purpose--scope)
- [⚙️ Goals & Constraints (Synthesised)](#-goals--constraints-synthesised)
- [🔍 Gaps & Improvement Opportunities](#-gaps--improvement-opportunities)
- [🛤️ Roadmap](#-roadmap)
- [☑️ Success Criteria](#-success-criteria)
- [📚 Related Documentation](#-related-documentation)

---

## 🎯 Purpose & Scope

This plan draws only on what the repository already states about itself — `README.md`, `ARCHITECTURE.md`,
`AGENTS.md`, `CLAUDE.md`, `CONTRIBUTING.md`, `HISTORY.md`'s Future Roadmap Implications section *(fill in: any other
top-level design doc, e.g. `UI.md`, plus the manifest, key config files and CI workflows, e.g. `package.json`/
`vite.config.ts` or `pom.xml`/`application*.properties`, and `.github/workflows`)* — rather than introducing new
goals. Where the documentation and the configuration disagree, or where a stated goal has no corresponding work item
yet, that gap is called out below as an improvement opportunity.

It complements, rather than duplicates, `HISTORY.md`'s "🛤️ Future Roadmap Implications" section: that section
tracks what changed release-to-release, while this document tracks the standing, cross-release gaps between the
project's stated intent and its current state.

Because the "⚙️ Goals & Constraints" table below is synthesised partly from `HISTORY.md`'s Future Roadmap
Implications section, check whether that table needs a matching update whenever `HISTORY.md` changes — most
concretely, whenever a release is being prepped and `HISTORY.md` gains its new Historical Timeline entry, per
`AGENTS.md`'s Release Checklist. *(reusable as-is)*

---

## ⚙️ Goals & Constraints (Synthesised)

*(fill in)* One row per stated goal or constraint, naming the doc/config it comes from (with the section in brackets
where useful). Once a goal is delivered, keep its row and append "— ✅ delivered in vX.Y.Z" rather than deleting it.

| Source                                        | Goal / constraint                                                                                   |
|-----------------------------------------------|-----------------------------------------------------------------------------------------------------|
| `README.md`, `AGENTS.md`                      | {{what the project is for, and any stated scope boundary — e.g. no backend in this repository}}     |
| `ARCHITECTURE.md` ({{section}})               | {{an architectural rule the codebase must keep — e.g. strict layering, feature-based organisation}} |
| `AGENTS.md` (Code Quality & CI)               | {{the automated gates that run, what triggers them and any enforced threshold}}                     |
| `AGENTS.md` (Git Workflow, Release Checklist) | {{the branching model and release process the project follows}}                                     |
| `AGENTS.md` (Documentation Conventions)       | {{British English, heading icons, evergreen `README.md`/`ARCHITECTURE.md`}}                         |
| `AGENTS.md` (Test Conventions)                | {{test framework, naming and structural rules}}                                                     |
| {{manifest file}}                             | {{a dependency/runtime currency constraint, e.g. tracking a framework's latest release closely}}    |

---

## 🔍 Gaps & Improvement Opportunities

Gaps are grouped by completion status — ✅ Completed, 🟡 Partially Completed, ⚪ Open — and numbered sequentially
across the whole document; a number is assigned once and never reused or resequenced, so it stays a gap's stable
identifier even after it moves between sections as its status changes (e.g. Open → Partially Completed → Completed).
Within each section, gaps stay in ascending number order. *(reusable as-is)*

Each gap looks for one of four things: a stated-but-unbuilt goal, a doc-vs-doc or doc-vs-code disagreement, a stale
number or a newly met precondition on an existing gap — see the `update-improvement-plan-gaps` skill.
*(reusable as-is)*

### 📋 At a Glance

*(fill in)* Keep this summary in step with the sections below — one line per gap, with its closing version or its
current Roadmap phase:

- **✅ Completed (0):** none yet.
- **🟡 Partially Completed (0):** none currently.
- **⚪ Open (1):**
  - #1 {{Gap title}} — current **Now** roadmap focus

### ✅ Completed

*No gaps have been completed yet.* A gap moves here once it reaches a final **Outcome**: its header gains a
"— ✅ Closed in vX.Y.Z" suffix (or "— ✅ Closed as not applicable in vX.Y.Z" if it was resolved by removing the
thing rather than delivering it), and its original Evidence/Why it matters/Proposed improvement paragraphs stay in
place above the new Outcome paragraph — never deleted or rewritten. *(reusable as-is)*

### 🟡 Partially Completed

*No gaps are currently partially completed.* A gap moves here when it has at least one **Progress** paragraph (per
`update-improvement-plan-gaps`'/`sync-improvement-plan-gaps`' "— 🟡 Partially completed in vX.Y.Z" header suffix)
but hasn't yet reached a final **Outcome** — it moves on to ✅ Completed once it does. *(reusable as-is)*

### ⚪ Open

*(fill in)* One `#### N. <Title>` section per gap, in this shape:

#### 1. {{Gap title — state the problem, not the fix}}

**Evidence:** {{the exact files, sections or lines that show the gap — quote the doc's own wording where it states
the gap itself, e.g. "still being built", "not yet wired", "TODO"}}

**Why it matters:** {{what goes wrong, or which stated goal is undermined, while the gap stays open}}

**Proposed improvement:** {{the concrete change that would close it — phased into numbered steps if it's large}}

---

## 🛤️ Roadmap

*(fill in)* Forward-looking priority, a separate concern from completion status above. Name each gap by number; say
"No items currently scoped" rather than leaving a phase blank.

| Phase       | Focus                                                                                       |
|-------------|---------------------------------------------------------------------------------------------|
| **Now**     | {{the gap currently being worked on}} (#1)                                                  |
| **Next**    | {{the gap queued behind it}}                                                                |
| **Later**   | {{lower-priority gaps, or "No items currently scoped"}}                                     |
| **Ongoing** | {{a recurring practice rather than a one-off fix — e.g. dependency review at each release}} |

---

## ☑️ Success Criteria

*(fill in)* One observable, checkable outcome per gap. Prefix a bullet with "✅ Met in vX.Y.Z:" once its gap closes,
rather than deleting it.

- {{an outcome that shows gap #1 is closed — e.g. "`build.yml` runs lint/build/test automatically on push/PR to
  `develop`/`main`"}}
- This document's Gaps section shrinks over time as items close — closed items should move into `HISTORY.md`'s
  Future Roadmap Implications section (or its Historical Timeline entries) rather than being deleted silently from
  here. *(reusable as-is)*

---

## 📚 Related Documentation

See `README.md`'s [📚 Documentation](/README.md#-documentation) section for the full documentation map. Most
relevant to this plan: *(reusable as-is — add any stack-specific doc this plan draws on, e.g. `UI.md`)*

- [`ARCHITECTURE.md`](/ARCHITECTURE.md) — the architectural rules and quality gates this plan builds on
- [`AGENTS.md`](/AGENTS.md) — the Git Workflow, Release Checklist and Roadmap Planning conventions referenced
  throughout
- [`HISTORY.md`](/HISTORY.md) — the "🛤️ Future Roadmap Implications" section this plan complements
- [`CONTRIBUTING.md`](/CONTRIBUTING.md) — contributor-facing setup and pull request checklist
- [`improvement-plan-tasks.md`](improvement-plan-tasks.md) — the checkbox-level task breakdown derived from this
  plan's gaps
