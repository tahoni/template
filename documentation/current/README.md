# AllTemplates Template

A reusable template repository providing a framework-agnostic `AGENTS.md` conventions file and a set of Claude Code
skills, ready to be filled in and dropped into any new software project.

## Table of Contents

- [📖 Introduction](#-introduction)
- [🔗 Repository](#-repository)
- [🧩 What's Inside](#-whats-inside)
- [🚀 Getting Started](#-getting-started)
- [📚 Documentation](#-documentation)
- [👤 Author](#-author)

---

## 📖 Introduction

This repository isn't a runnable application — it's a **template**. It packages the framework-agnostic parts of two
sibling projects' own conventions (`hpsc-web-vite`, a React/Vite frontend, and `hpsc-web-springboot`, a Spring Boot
backend) into a single, reusable `AGENTS.md` conventions file, a thin `CLAUDE.md` pointer to it and eight Claude Code
skills that turn its conventions into ready-to-invoke workflows. Copy this repository's contents into a new project
and fill in its `*(fill in)*`-marked sections with that project's own tech stack, commands and structure.

---

## 🔗 Repository

The repository for this project is located at [GitHub](https://github.com/tahoni/template).

Feature requests, suggestions for improvements and bugs can be logged using the project's
[Issues](https://github.com/tahoni/template/issues) page.

---

## 🧩 What's Inside

| Path                                          | Purpose                                                                                                                                                                                                                                                                                                         |
|-------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `AGENTS.md`                                      | The full conventions file — project overview, tech stack, build/run commands, environment variables, architecture, code quality & CI, documentation conventions, documentation file map, roadmap planning, Claude Code skills, test conventions, directory tree maintenance, git workflow and release checklist |
| `CLAUDE.md`                                      | Thin pointer to `AGENTS.md`, kept only because Claude Code specifically looks for a file by that name                                                                                                                                                                                                           |
| `README.md`, `ARCHITECTURE.md`, `CONTRIBUTING.md`, `HISTORY.md`, `CHANGELOG.md`, `RELEASE_NOTES.md`, `LICENSE.md` | Fill-in-template scaffolds for a scaffolded project's own copies of these files, per `AGENTS.md`'s Documentation File Map — `README.md`/`HISTORY.md`/`CHANGELOG.md`/`RELEASE_NOTES.md` are distinct from this template repository's own real versions, which live in `documentation/current/` (see below) |
| `UI.md`                                          | Optional fill-in-template scaffold for a component-based frontend project's UI/layout documentation — delete rather than fill in for a non-frontend project, per `AGENTS.md`'s Documentation File Map |
| `PACKAGES.md`                                    | Optional fill-in-template scaffold for a dependency/funding manifest (e.g. `npm fund` output) — delete rather than fill in for a project whose package manager has no equivalent tooling, per `AGENTS.md`'s Documentation File Map |
| `.claude/skills/`                                | Eight Claude Code skills automating `AGENTS.md`'s conventions — see its 🧩 Claude Code Skills section for the full list                                                                                                                                                                                         |
| `.gitignore`, `.aiignore`                        | Baseline ignore patterns                                                                                                                                                                                                                                                                                        |

---

## 🚀 Getting Started

1. Copy `AGENTS.md`, `CLAUDE.md`, `README.md`, `ARCHITECTURE.md`, `CONTRIBUTING.md`, `HISTORY.md`, `CHANGELOG.md`,
   `RELEASE_NOTES.md`, `LICENSE.md`, `.claude/skills/`, `.gitignore` and `.aiignore` into the new project's
   repository root.
2. Work through `AGENTS.md` top to bottom, replacing every `*(fill in)*`/`*(fill in, if applicable)*` section with
   the project's own tech stack, commands, architecture and environment variables — sections marked
   `*(reusable as-is)*` need no changes. Do the same for the other seven files above, choosing an actual licence
   (or swapping in a different one entirely) for `LICENSE.md`.
3. Copy `UI.md` and `PACKAGES.md` too, but only where each applies — `UI.md` for a component-based frontend,
   `PACKAGES.md` for a package manager with equivalent funding-tree tooling — deleting whichever one doesn't rather
   than leaving it unfilled.
4. Start using the `.claude/skills/` — each one reads `AGENTS.md` in full before acting, so once it's filled in the
   skills work without further setup.

---

## 📚 Documentation

This template's own documentation is spread across a few files, each with a distinct purpose:

| File                                   | Purpose                                                                                         |
|----------------------------------------|-------------------------------------------------------------------------------------------------|
| [`README.md`](README.md)               | This file                                                                                       |
| [`AGENTS.md`](/AGENTS.md)              | The conventions template itself — the source of truth this file points to                       |
| [`CLAUDE.md`](/CLAUDE.md)              | Thin pointer to `AGENTS.md`                                                                     |
| [`CHANGELOG.md`](CHANGELOG.md)         | Notable changes per release, in [Keep a Changelog](https://keepachangelog.com/en/1.0.0/) format |
| [`HISTORY.md`](HISTORY.md)             | Narrative history of this template's own evolution                                              |
| [`RELEASE_NOTES.md`](RELEASE_NOTES.md) | Detailed release notes for the current/latest version                                           |

All four of these files (this one included) live in `documentation/current/`, not the repository root — see
`AGENTS.md`'s Documentation File Map for why.

[`documentation/history/`](/documentation/history) archives past releases' `RELEASE_NOTES_vX.Y.Z.md`/
`PR_DESCRIPTION_vX.Y.Z.md` files, grouped into one subdirectory per major version (e.g.
`documentation/history/v1/`), so past releases stay individually referenceable once `RELEASE_NOTES.md` moves on to
the next version, plus one standing exception —
[`EVOLUTION_OVERVIEW.md`](/documentation/history/EVOLUTION_OVERVIEW.md), `HISTORY.md`'s companion holding the full
Phase-by-phase narrative, split out to keep `HISTORY.md` a manageable size.

`ARCHITECTURE.md`, `CONTRIBUTING.md` and `LICENSE.md` — named in `AGENTS.md`'s own Documentation File Map — don't
exist yet for this template repository itself; they're intended for the projects scaffolded from it, per the
Getting Started steps above.

This template follows [Semantic Versioning 2.0.0](https://semver.org/) (`MAJOR.MINOR.PATCH`).

---

## 👤 Author

**Leoni Lubbinge**

- [![Gmail Badge](https://img.shields.io/badge/tahoni%40gmail.com-blue?logo=gmail)](mailto:tahoni@gmail.com)
- [![GitHub Badge](https://img.shields.io/badge/Leoni_Lubbinge-blue?logo=github)](https://github.com/tahoni)
