---
name: scaffold-unit-tests
description: Scaffold unit tests for a component, class, function, hook or helper, isolated from its heavier/third-party dependencies, following this project's testing conventions. Use whenever the user asks to add/scaffold/write unit tests for one or more of these.
user-invocable: true
allowed-tools:
  - Read
  - Write
  - Edit
  - Glob
  - Grep
---

# Scaffold Unit Tests

The target name(s) or file path(s) to scaffold tests for (one or more, space- or comma-separated) are passed as
`args`.

*(fill in)* Add the stack's own test-runner/build `Bash` entries to `allowed-tools` above — e.g.
`Bash(npx vitest run:*)` and `Bash(npm run lint:*)` for a Vitest/ESLint frontend, or `Bash(./mvnw test:*)` for a
Maven/JUnit backend.

## 🔍 Gather current state

1. Read `AGENTS.md` in full for conventions.
2. *(fill in, if applicable)* Check the test infrastructure actually exists before scaffolding against it — e.g. a
   test runner is declared as a dependency but has no config file, environment or supporting test-utility packages
   installed yet. If so, set it up once (config file, environment, setup/helper module) before scaffolding the first
   test, and treat that as a one-time step to skip on future runs.

## 🚀 Instructions

Read and strictly follow **all conventions defined in AGENTS.md** — in particular its **Test Conventions** and
**Architecture** sections. Treat it as the single source of truth; do not reinterpret or contradict its rules.

1. **Resolve `args` to one or more targets.** Split on commas and/or whitespace; each token is a name or a file path
   under the project's source root — search by name with Glob/Grep if a bare name was given rather than a path. If
   `args` is empty, ask the user which target(s) to scaffold rather than guessing. Repeat steps 2–7 independently for
   each resolved target — a failure or ambiguity on one target (not found, name matches multiple candidates) must not
   block scaffolding the others; report it and move on.
2. **Determine where each target's test(s) belong**, per AGENTS.md's Test Conventions (co-located next to the source
   file, or mirrored under a dedicated test root — whichever this project's language/tooling convention is) and its
   naming pattern (e.g. `<Name>.test.ts(x)`, `<ClassName>Test.java`). *(fill in)* Name this project's specific
   target categories and their exact test-file locations/naming — for example:
   - *Frontend inspiration:* component/layout → `<Name>.test.tsx` in the component's own folder; utility → `<name>.test.ts`
     alongside the source; hook → tested via a render-hook utility.
   - *Backend inspiration:* an interface and its implementation get **separate** test classes when both carry
     independent logic (e.g. `XService` → `XServiceTest` against the interface/mocked collaborators; `XServiceImpl`
     → `XServiceImplTest` for impl-only helper methods) — otherwise a single `<ClassName>Test`, mirroring the
     target's package under the test root.
3. **Isolate the target from its heavier/third-party dependencies** — this is what makes it a *unit* test, as opposed
   to a full-tree/integration test (see the `scaffold-integration-tests` skill):
   - Mock true external-service boundaries (network calls, third-party SDKs, email/notification senders, maps/calendar
     widgets, anything reaching outside the process).
   - Mock sibling collaborators the target composes or depends on (so a failure in a collaborator doesn't surface as
     a failure in this target's test) — but don't mock away the minimal scaffolding needed just to construct/render
     the target (e.g. a router/DI context it genuinely needs).
   - Do not mock the target's own direct inputs/parameters/props away — test them.
4. **Don't test generated or trivial pass-through behaviour** — per AGENTS.md's Test Conventions, skip
   language/framework/ORM-generated members (constructors, getters/setters, `toString()`/`equals()`/`hashCode()`,
   builders) and type-system-only checks with no accompanying custom logic. Using such generated members incidentally
   to build fixtures or assert real behaviour is fine; only test them directly when they're handwritten or add real
   logic.
5. **Cover real behaviour**: valid inputs, edge cases (empty/null/undefined/blank) and error paths, asserting on
   observable output/behaviour rather than internal state. *(fill in, if applicable)* Note any project-specific
   assertion idiom (e.g. asserting against a custom exception hierarchy; querying rendered output by role/text rather
   than snapshotting).
6. **Match the existing style exactly** — an Arrange-Act-Assert structure with comments per AGENTS.md's Test
   Conventions (grouped/ordered by member under test, private helpers moved to the end under `// Helpers`), mirroring
   the closest existing sibling test file rather than inventing a new style. Where this skill is establishing the
   very first test file in an area, follow AGENTS.md's Test Conventions directly.
7. **Run each new/extended test file as it's finished**, then run the full suite once at the end and confirm
   everything passes before finishing. *(fill in)* the exact commands, e.g.:
   ```bash
   <test-runner> <path/to/single-test-file>
   <test-runner>            # full suite
   <linter>                 # if the stack has a separate lint gate the new files must satisfy
   ```
8. **Update `CHANGELOG.md`** under the Unreleased section in the same change, per AGENTS.md's Git Workflow
   conventions — one entry per target if their scope differs, or a single combined entry if they're closely related
   — only if the change is notable enough to warrant an entry.
9. **Do not run `git add`, `git commit` or `git push` yourself** — this skill only scaffolds and verifies; leave the
   new/changed files for the user to review and commit.

## 📤 Output

For each target: which test file(s) were created or extended and a one-line summary of what each covers (or, if the
target couldn't be resolved/scaffolded, why). Note whether any test infrastructure was newly set up this run. Finish
with the overall test-run result (pass/fail counts) and, if applicable, the lint result. Do not commit anything —
say so if asked.
