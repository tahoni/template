# {{Project Name}} User Interface

*(fill in)* One or two sentences describing what this document covers: an overview of the user interface for
{{the project}}.

This file is a **template** — see `AGENTS.md`'s Documentation File Map, which names this as a stack-specific doc
for a component-based frontend (alongside `PACKAGES.md`/`HELP.md` for other stacks). Every section below is either
directly reusable as-is (marked *(reusable as-is)*) or a scaffold to fill in for the specific project (marked
*(fill in)*) — replace the bracketed guidance with the project's own details and delete these template notes once
done. If this project isn't a component-based frontend, delete this file entirely rather than leaving it unfilled.

## Table of Contents

- [🎨 Design Philosophy](#-design-philosophy)
- [📐 Layout Structure](#-layout-structure)
    - [🔝 Header](#-header)
    - [📄 Body](#-body)
    - [⬇️ Footer](#-footer)
- [🛣️ Navigation](#-navigation)
- [📱 Responsive Design](#-responsive-design)
- [💻 Technical Implementation](#-technical-implementation)
- [👤 Designers](#-designers)

---

## 🎨 Design Philosophy

*(fill in)* One or two sentences on the overall design intent — e.g. what the UI optimises for (accessibility,
information density, brand consistency) and who its primary audience is.

---

## 📐 Layout Structure

*(fill in, if applicable)* The application's top-level layout shape and the shared component that implements it
(e.g. a `Layout` component). A common shape is three-part:

1. **Header**: {{fill in — branding, primary navigation, etc.}}
2. **Body**: {{fill in — the main content area and any sidebars}}
3. **Footer**: {{fill in — contact info, links, copyright}}

### 🔝 Header

*(fill in)* What the header contains and how it behaves (fixed/sticky, responsive collapse, etc.).

### 📄 Body

*(fill in)* The main content area's shape — how it adapts to different page types, any sidebar/slot pattern used.

### ⬇️ Footer

*(fill in)* What the footer contains — links, contact details, legal/copyright notice, social links.

---

## 🛣️ Navigation

*(fill in)* The primary navigation menu's routes, one bullet per route with a short description of what it leads
to. Note separately any route that's reachable by direct URL but deliberately excluded from the primary navigation
menu (e.g. a contact page, a page only linked from elsewhere).

---

## 📱 Responsive Design

*(fill in)* The responsive strategy and the UI framework/breakpoints it relies on — e.g. a CSS framework's grid
system and how navigation/layout adapt at each breakpoint (a collapsing "hamburger" menu on small screens, a
sidebar that moves below the main content, etc.).

---

## 💻 Technical Implementation

*(fill in)* A bullet list of the UI-specific stack — mirror `AGENTS.md`'s Tech Stack section, but scoped to
presentation concerns:

```
- **Framework**: {{UI framework}}
- **Styling**: {{styling approach/framework}}
- **Icons**: {{icon library, if any}}
- **Content**: {{how content-heavy pages are authored, e.g. components vs. MDX/CMS}}
- **Routing**: {{client-side routing library}}
```

---

## 👤 Designers

*(fill in)* Name(s) and contact/profile links of whoever owns the UI/UX design, if distinct from the engineering
Author(s) in `README.md`.

**{{Designer Name}}**

- [![Gmail Badge](https://img.shields.io/badge/{{email}}-blue?logo=gmail)](mailto:{{email}})
