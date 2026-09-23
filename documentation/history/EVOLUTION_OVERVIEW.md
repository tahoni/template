# Template Evolution Overview

`HISTORY.md`'s companion — the full Phase-by-phase narrative behind this template's evolution, split out here to
keep `HISTORY.md` a manageable size. See [`HISTORY.md`](/documentation/current/HISTORY.md) for the Historical
Timeline, Key Learnings, Future Roadmap Implications and Conclusion.

---

## 📖 Evolution Overview

### Phase 1 — Combining Two Sibling Projects' Conventions (v1.0.0)

This template began as an extraction exercise: `hpsc-web-vite` (a React/Vite frontend) and `hpsc-web-springboot` (a
Spring Boot backend) had each independently developed their own `AGENTS.md` and `.claude/skills/` set, covering the
same underlying workflow — GitFlow branching, a Keep a Changelog `CHANGELOG.md`, a structured `RELEASE_NOTES.md`, a
narrative `HISTORY.md`, roadmap gap tracking and a shared set of documentation conventions (British English, serial
commas, an icon registry for headings). Rather than picking one project's version as the template, v1.0.0 merged the
genuinely framework-agnostic parts of both into a single file, marking every section *(reusable as-is)* or
*(fill in)* so a new project adopting the template knows exactly what to replace. The same merge produced eight
Claude Code skills, each trimmed to defer to `AGENTS.md` for any convention it shares rather than restating it — a
discipline that keeps the two from drifting apart as `AGENTS.md` itself changes.

### Phase 2 — Staying in Sync with the Sibling Projects (v1.1.0)

Once the sibling `hpsc-web-springboot` project kept evolving independently, its own `AGENTS.md`/skills accumulated
conventions this template didn't yet have: an optional way to keep `documentation/history/` navigable once a
project's release archive grows into the dozens of files, and a formal description of the three-tier test split a
layered, interface-based backend naturally falls into. v1.1.0 establishes the pattern this template will keep
following — periodically diffing a sibling project's `AGENTS.md`/skill history against the point this template last
synced from it, and pulling forward only the conventions that are genuinely reusable across any project, not the
sibling's own project-specific detail.

### Phase 3 — Making the Evolution Overview Split Mandatory (Unreleased)

`hpsc-web-springboot` itself only split its Evolution Overview out of `HISTORY.md` once the section had grown to
roughly half that file's size — an optional, reactive scaling step. This template instead makes the split mandatory
from the very first release: `HISTORY.md`'s "📖 Evolution Overview" section is always just a pointer to this file,
never the narrative itself, so `HISTORY.md` stays a manageable size by construction rather than needing a
disruptive one-off reorganisation later. `AGENTS.md`'s Documentation File Map, Release Checklist and the
`prep-version-release` skill are updated to match — every future release's Phase entry lands here, never in
`HISTORY.md`.

---

**For the Historical Timeline, Key Learnings, Future Roadmap Implications and Conclusion, see
[HISTORY.md](/documentation/current/HISTORY.md)**
