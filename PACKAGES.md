# {{Project Name}} Packages Funding Tree

*(fill in)* This document lists the packages used in the project that are seeking funding.

This file is a **template** — see `AGENTS.md`'s Documentation File Map, which names this as a stack-specific doc for
a dependency/funding manifest (alongside `UI.md`/`HELP.md` for other stacks). Every section below is either directly
reusable as-is (marked *(reusable as-is)*) or a scaffold to fill in for the specific project (marked *(fill in)*) —
replace the bracketed guidance with the project's own details and delete these template notes once done. If this
project's package manager has no equivalent funding-tree tooling (e.g. `npm fund`), delete this file entirely
rather than leaving it unfilled.

## Table of Contents

- [📖 Introduction](#-introduction)
- [💰 Packages looking for funding](#-packages-looking-for-funding)
- [💰 Subscriptions to packages looking for funding](#-subscriptions-to-packages-looking-for-funding)
- [💰 Future subscriptions to packages looking for funding](#-future-subscriptions-to-packages-looking-for-funding)

---

## 📖 Introduction

If you find the following packages useful, please consider supporting their development by visiting the provided
links. Open source software relies heavily on the contributions of developers who often work voluntarily.
Supporting these developers helps ensure the sustainability and continued improvement of the software.
*(reusable as-is)*

---

## 💰 Packages looking for funding

*(fill in)* The full funding tree for every dependency that has a `funding` field, generated rather than
handwritten — e.g. via `{{package manager}} fund` for an npm-based project — pasted verbatim into a fenced code
block below, headed by the project's own `name@version`:

```
{{package-name}}@{{version}}
```

```html
├─── <a href="{{funding URL}}"></a>
│                   └─── {{dependent package}}@{{version}}
```

---

## 💰 Subscriptions to packages looking for funding

*(fill in, if applicable)* The same tree as above, annotated with what this project actually pledges/subscribes to
fund for each entry (e.g. `$5`, `custom amount=$5` or left blank for ones not yet supported):

```html
├─── <a href="{{funding URL}}">{{pledge amount, or blank}}</a>
│                   └─── {{dependent package}}@{{version}}
```

---

## 💰 Future subscriptions to packages looking for funding

*(fill in, if applicable)* Packages the project intends to start funding but hasn't yet — same shape as the
sections above, moved here as a holding area until the subscription is actually set up, then moved into
"Subscriptions to packages looking for funding" once it is.
