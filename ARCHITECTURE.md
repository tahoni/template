# {{Project Name}} Architecture

*(fill in)* One or two sentences describing what this document covers: the architectural design, directory
structure and core concepts of the project.

This file is a **template**. Every section below is either directly reusable as-is (marked *(reusable as-is)*) or a
scaffold to fill in for the specific project (marked *(fill in)*) — replace the bracketed guidance with the
project's own details and delete these template notes once done.

## Table of Contents

- [⚙️ Technology Stack](#-technology-stack)
- [📁 Project Structure](#-project-structure)
- [🎯 System Overview](#-system-overview)
- [🏛️ Core Architecture](#-core-architecture)
- [🧭 Key Design Patterns](#-key-design-patterns)
- [🔃 Data Flow](#-data-flow)
- [✅ Quality Attributes](#-quality-attributes)
- [🔬 CI/CD & Quality Gates](#-cicd--quality-gates)
- [🛠️ Development Guidelines](#-development-guidelines)

---

## ⚙️ Technology Stack

*(fill in)* A table of the language, framework, build tool and other core technologies — mirror `AGENTS.md`'s Tech
Stack section, naming the tool rather than a pinned version:

| Component | Technology     |
|-----------|----------------|
| Framework | {{framework}}  |
| Language  | {{language}}   |
| Build     | {{build tool}} |

---

## 📁 Project Structure

*(fill in)* A directory tree of the repository's top-level structure — see `AGENTS.md`'s Directory Tree Maintenance
section for the rules this tree must follow (no enumerated files/classes, no gitignored directories, tracked
tooling directories included):

```
{{project-root}}/
├── {{src-dir}}/          {{one-line, generic role description}}
├── .claude/               Claude Code skills (see AGENTS.md's Claude Code Skills section)
├── documentation/         Supplementary docs (history, roadmap, recommendations — see AGENTS.md's Documentation
                            File Map)
└── ...
```

---

## 🎯 System Overview

*(fill in)* One or two paragraphs describing the system's overall shape and responsibilities at a level above
individual layers/components — what problem it solves and how the pieces fit together.

---

## 🏛️ Core Architecture

*(fill in)* Expand on `AGENTS.md`'s Architecture section's flow diagram with a detailed, layer-by-layer (or
component-by-component) breakdown — one `###` subsection per layer/component, each covering its responsibility,
the technology it uses and any conventions specific to it. For a layered backend, this typically means Presentation
→ Service → Persistence → Model, plus supporting concerns (validation, exception handling); for a component-based
frontend, this typically means Routing → Feature pages → Feature content → Shared components/layouts.

---

## 🧭 Key Design Patterns

*(fill in, if applicable)* Notable design patterns used throughout the codebase and why (e.g. a Repository pattern,
a Strategy pattern for pluggable behaviour, a Provider/Context pattern for shared frontend state).

---

## 🔃 Data Flow

*(fill in)* One diagram per notable flow — the typical request/response path at minimum, plus any distinctive
flow the project has (e.g. a bulk import, an async job, a client-side cache invalidation path):

```
{{Entry point}}
    → {{step}}
    → {{step}}
    → {{destination}}
```

---

## ✅ Quality Attributes

*(fill in, if applicable)* Non-functional properties the architecture is designed around — e.g. statelessness,
idempotency, a specific performance/latency target, accessibility, offline support — and the concrete design choice
behind each.

---

## 🔬 CI/CD & Quality Gates

See `AGENTS.md`'s Code Quality & CI section for the automated gates (static analysis, linting, build workflow,
dependency audit). *(reusable as-is)*

---

## 🛠️ Development Guidelines

See `AGENTS.md`'s Code Style, Test Conventions and Git Workflow sections for the conventions that apply when
extending this architecture. *(reusable as-is)*
