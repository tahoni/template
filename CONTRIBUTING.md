# Contributing to {{Project Name}}

*(fill in)* One short sentence welcoming contributors and pointing at the essentials below.

This file is a **template**. Every section below is either directly reusable as-is (marked *(reusable as-is)*) or a
scaffold to fill in for the specific project (marked *(fill in)*) — replace the bracketed guidance with the
project's own details and delete these template notes once done.

## Table of Contents

- [📋 Prerequisites](#-prerequisites)
- [🚀 Getting Started](#-getting-started)
- [🧪 Testing](#-testing)
- [🏛️ Architecture at a Glance](#-architecture-at-a-glance)
- [🧩 Claude Code Skills](#-claude-code-skills)
- [✍️ Documentation Conventions](#-documentation-conventions)
- [🛤️ Roadmap](#-roadmap)
- [🔀 Git Workflow](#-git-workflow)
- [🔬 CI/CD & Quality Gates](#-cicd--quality-gates)
- [☑️ Pull Request Checklist](#-pull-request-checklist)
- [🚢 Cutting a Release](#-cutting-a-release)
- [💬 Questions & Support](#-questions--support)

---

## 📋 Prerequisites

*(fill in)* Runtime/tooling versions and accounts needed before setting up a local development environment — mirror
`AGENTS.md`'s Tech Stack/Environment Variables sections.

---

## 🚀 Getting Started

*(fill in)* Clone, install and run the project locally — mirror `AGENTS.md`'s Build & Run Commands section:

```bash
git clone {{repo URL}}
cd {{project directory}}

# Install dependencies

# Run the dev server / application
```

---

## 🧪 Testing

Run the test suite before opening a pull request. See `AGENTS.md`'s Test Conventions section for the structural
rules new tests must follow (Arrange-Act-Assert, grouping/ordering by member under test, helpers moved to the
end). *(reusable as-is)*

```bash
# Run the test suite
```

*(fill in)* the actual test command(s) above.

---

## 🏛️ Architecture at a Glance

See [`ARCHITECTURE.md`](ARCHITECTURE.md) for the full design. *(reusable as-is)*

---

## 🧩 Claude Code Skills

`.claude/skills/` holds ready-to-invoke workflows that automate this project's conventions — see `AGENTS.md`'s
Claude Code Skills section for the full list and what each one does. *(reusable as-is)*

---

## ✍️ Documentation Conventions

British English spelling, serial commas (no comma before the final `and`/`or` in a list of three or more) and the
icon-prefixed heading style — see `AGENTS.md`'s Documentation Conventions section for the full rules and the icon
registry. *(reusable as-is)*

---

## 🛤️ Roadmap

`documentation/roadmap/improvement-plan.md` and `improvement-plan-tasks.md` track this project's active
improvement backlog — check both before assuming a gap (missing tests, no CI, etc.) is unintentional; it may
already be tracked there. See `AGENTS.md`'s Roadmap Planning section for the file structure and status-transition
rules. *(reusable as-is)*

---

## 🔀 Git Workflow

This project follows the branching model, merge strategy and commit conventions documented in `AGENTS.md`'s Git
Workflow section — branch from and PR into the branch that section names as the day-to-day integration branch,
commit in logical chunks and update `CHANGELOG.md`'s `### 🧪 [Unreleased]` section in the same change as the code
it documents. *(reusable as-is)*

---

## 🔬 CI/CD & Quality Gates

See `AGENTS.md`'s Code Quality & CI section for the automated gates a pull request must pass. *(reusable as-is)*

---

## ☑️ Pull Request Checklist

*(fill in, if applicable)* Add any project-specific checklist items beyond the reusable baseline below:

- [ ] Tests added/updated and passing, per the Testing section above
- [ ] `CHANGELOG.md`'s `### 🧪 [Unreleased]` section updated, per `AGENTS.md`'s Git Workflow Conventions
- [ ] Documentation (`README.md`, `ARCHITECTURE.md`, doc comments) updated for any behaviour this PR changes
- [ ] No `*(fill in)*`-marked template scaffolding left unfilled in any file this PR touches

---

## 🚢 Cutting a Release

See `AGENTS.md`'s Release Checklist section for the full, ordered set of steps — the `prep-version-release` Claude
Code skill automates it end to end. *(reusable as-is)*

---

## 💬 Questions & Support

*(fill in, if applicable)* Where to ask questions or report issues — e.g. the repository's
[Issues]({{repo URL}}/issues) page.
