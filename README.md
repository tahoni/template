# {{Project Name}}

*(fill in)* One short sentence describing what the project is and who it's for — the human-facing counterpart to
`AGENTS.md`'s Project Overview section.

This file is a **template**. Every section below is either directly reusable as-is (marked *(reusable as-is)*) or a
scaffold to fill in for the specific project (marked *(fill in)*) — replace the bracketed guidance with the
project's own details and delete these template notes once done.

## Table of Contents

- [📖 Introduction](#-introduction)
- [🔗 Repository](#-repository)
- [⚙️ Technology](#-technology)
- [🚀 Instructions](#-instructions)
    - [📋 Prerequisites](#-prerequisites)
    - [🔧 Installation and Execution](#-installation-and-execution)
- [🏛️ Architecture](#-architecture)
- [📚 Documentation](#-documentation)
    - [🛤️ Roadmap](#-roadmap)
- [📜 Licence](#-licence)
- [👤 Author](#-author)

---

## 📖 Introduction

*(fill in)* One or two paragraphs: what the project does, who it's for and the main capabilities it currently
provides — mirror `AGENTS.md`'s Project Overview section, but written for a human reader landing on the repo rather
than an agent. Note plainly whether this repository is standalone or one half of a paired frontend/backend system,
linking the other half if so.

---

## 🔗 Repository

*(fill in, if applicable)* The repository for this project is located at [GitHub]({{repo URL}}).

Feature requests, suggestions for improvements and bugs can be logged using the project's
[Issues]({{repo URL}}/issues) page.

---

## ⚙️ Technology

*(fill in)* A bullet list of the language, framework, build tool and notable libraries — mirror `AGENTS.md`'s Tech
Stack section (same content, human-facing framing):

```
- **Framework**: {{framework}}
- **Language**: {{language}}
- **Build Tool**: {{build tool}}
- **Testing**: {{test framework(s)}}
```

---

## 🚀 Instructions

### 📋 Prerequisites

*(fill in)* Runtime/tooling versions and accounts needed before installing (e.g. a specific Node/Java version, a
database server, an API key).

### 🔧 Installation and Execution

*(fill in)* The minimal steps to install and run the project — mirror `AGENTS.md`'s Build & Run Commands section:

```bash
# Install dependencies

# Run the dev server / application

# Run the test suite
```

---

## 🏛️ Architecture

A detailed explanation of the architecture can be found in the [`ARCHITECTURE.md`](ARCHITECTURE.md) file.
*(reusable as-is)*

---

## 📚 Documentation

This project's documentation is spread across a few files, each with a distinct purpose. *(reusable as-is — keep
this table in sync with `AGENTS.md`'s Documentation File Map, the canonical version if the two ever drift)*

| File                                    | Purpose                                                                        |
|------------------------------------------|--------------------------------------------------------------------------------|
| [`README.md`](README.md)                 | Project overview, setup and links to the rest of the documentation (this file) |
| [`ARCHITECTURE.md`](ARCHITECTURE.md)      | Detailed architectural design, directory/package structure and core concepts   |
| [`CLAUDE.md`](CLAUDE.md)                  | Thin pointer to `AGENTS.md`, kept for tools that specifically read `CLAUDE.md` |
| [`AGENTS.md`](AGENTS.md)                  | Cross-tool agent conventions — the full guidance                              |
| [`CONTRIBUTING.md`](CONTRIBUTING.md)      | Contributor-facing setup, git workflow and pull request checklist              |
| [`CHANGELOG.md`](CHANGELOG.md)            | Notable changes per released version, in Keep a Changelog format               |
| [`HISTORY.md`](HISTORY.md)                | Narrative history of the project's evolution across all versions               |
| [`RELEASE_NOTES.md`](RELEASE_NOTES.md)    | Detailed release notes for the current/latest version only                     |
| [`LICENSE.md`](LICENSE.md)                | Project licence                                                                |

*(fill in, if applicable)* Add stack-specific docs the project needs — e.g. `UI.md`, `PACKAGES.md`, `HELP.md` — per
`AGENTS.md`'s Documentation File Map.

[`documentation/history/`](documentation/history) archives past releases' `RELEASE_NOTES_vX.Y.Z.md`/
`PR_DESCRIPTION_vX.Y.Z.md` files, so past releases stay individually referenceable once `RELEASE_NOTES.md` moves on
to the next version. *(reusable as-is)*

### 🛤️ Roadmap

[`documentation/roadmap/`](documentation/roadmap) holds in-progress planning documents — not part of the standard
documentation set above, and not required reading to work in this repository. *(reusable as-is)*

This project follows [Semantic Versioning 2.0.0](https://semver.org/) (`MAJOR.MINOR.PATCH`). *(reusable as-is)*

---

## 📜 Licence

The copyright licence can be found in the [`LICENSE.md`](LICENSE.md) file. *(reusable as-is)*

---

## 👤 Author

*(fill in)* Name and contact/profile links.

**{{Author Name}}**

- [![GitHub Badge](https://img.shields.io/badge/{{handle}}-blue?logo=github)]({{GitHub profile URL}})
