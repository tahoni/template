---
name: scaffold-integration-tests
description: Scaffold integration tests that exercise a target through its real internal wiring (not isolated/mocked collaborators), following this project's testing conventions. Use whenever the user asks to add/scaffold/write integration tests for one or more classes, services, components, routes or pages.
user-invocable: true
allowed-tools:
  - Read
  - Write
  - Edit
  - Glob
  - Grep
  # (fill in) add the project's own test-runner and lint/verify Bash patterns, e.g.:
  #   Bash(npx vitest run:*)   — Vite/Vitest frontend
  #   Bash(./mvnw test:*)      — Maven/Spring Boot backend
  #   Bash(npm run lint:*)
---

# Scaffold Integration Tests

The target(s) to scaffold tests for (one or more, space- or comma-separated — classes, services, routes, pages or
file paths, whichever unit this project's integration tests are built around) are passed as `args`.

Read `AGENTS.md` in full before starting.

## 🚀 Instructions

Read and strictly follow **all conventions defined in AGENTS.md** — in particular its **Test Conventions** and
**Architecture** sections. Treat it as the single source of truth; do not reinterpret or contradict its rules.

*(fill in)* Define what "integration test" means for this project's own architecture — i.e. which real internal
boundary it exercises, as opposed to the isolated, dependency-mocked units `scaffold-unit-tests` produces. Two
illustrative (not prescriptive) examples of how prior projects answered this:

- A component-based frontend with no backend of its own: the boundary is the **full composed component/route
  tree** (e.g. router → layout → page → content → shared components), rendered for real end-to-end.
- A backend service layer: the boundary is a **real, framework-wired bean** (service and/or repository) running
  against a real (or in-memory/test-profile) database, called only through its public interface.

Whatever this project's boundary is, the same shared rules apply:

1. **Resolve `args` to one or more targets.** Split on commas and/or whitespace; look each one up by name/path with
   Glob/Grep if a bare identifier was given rather than a full path. If `args` is empty, ask the user which
   target(s) to scaffold rather than guessing. Repeat steps 2–8 independently for each resolved target — a failure
   or ambiguity on one target must not block scaffolding the others; report it and move on.
2. **Create or extend the integration test file**, following this project's own naming/location convention for
   integration tests (e.g. a `.integration.test.*` suffix co-located with the source file, or a dedicated
   `*IntegrationTest` class in a parallel test tree) — *(fill in)* the exact convention and any required
   annotations/setup (e.g. a test profile, a lightweight context configuration) — and mirror the closest existing
   sibling integration test rather than inventing a new shape.
3. **Wire the real internal path**, not a mocked stand-in for this project's own code — render the actual
   component tree / instantiate the actual framework-wired bean(s), so every internal collaborator on that path
   runs for real.
4. **Mock only genuine external-service boundaries** — third-party APIs, network calls, external systems this
   project doesn't own (maps, calendars, bot-protection widgets, outbound email/HTTP calls, etc.). **Never mock
   this project's own internal components, classes or collaborators** — that defeats the point of an integration
   test. Reuse a shared mock helper (rather than duplicating one) if more than one target needs the same boundary
   mocked.
5. **Only exercise the target's public contract** — call it exactly as a real caller would (its exported
   component/route, or its interface's public methods), never reaching into protected/private internals via
   casts, reflection or test-only backdoors; those are the paired unit test's job.
6. **Cover the target's full observable behaviour end-to-end**: primary happy paths, edge cases/format quirks
   specific to the target, and error paths — asserting via this project's own conventions (rendered output,
   thrown-exception hierarchy, persisted state, etc.), more thoroughly than the corresponding unit test.
7. **Don't duplicate the paired unit test's narrower, isolated-collaborator coverage** (from `scaffold-unit-tests`,
   if one exists for the same target) — this skill's job is the deeper, real-wiring sweep, not re-testing an
   individual collaborator's own isolated behaviour.
8. **Follow AGENTS.md's Test Conventions for everything structural** — don't test framework/language/ORM-generated
   trivial behaviour, Arrange-Act-Assert structure, method/route-under-test grouping, and private helpers moved to
   the end under `// Helpers`. Don't restate those rules here; just apply them.
9. **Run each new/extended test file/class as it's finished**, then run the full suite once at the end and confirm
   everything passes before finishing — *(fill in)* this project's actual test-runner and lint/verify commands.
10. **Update `CHANGELOG.md`** under its `### 🧪 [Unreleased]` section in the same change, per AGENTS.md's Git
    Workflow Conventions (`#### <category>` → `##### <Area>`) — one entry per target if their scope differs, or a
    single combined entry if they're closely related — only if the change is notable enough to warrant an entry.
11. **Do not run `git add`, `git commit` or `git push` yourself** — this skill only scaffolds and verifies; leave
    the new/changed files for the user to review and commit.

## 📤 Output

For each target: which test file(s) were created or extended and a one-line summary of what each covers (or, if the
target couldn't be resolved/scaffolded, why). Note whether any shared external-service mock helper was newly added
this run. Finish with the overall test-run result (pass/fail counts). Do not commit anything — say so if asked.
