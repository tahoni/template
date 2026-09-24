# Release Notes – Version {{X.Y.Z}}

*(fill in)* Unlike `CHANGELOG.md`, this file holds only the **current** release — replaced outright (not appended
to) each time a new version ships. Once finalised, archive a byte-for-byte copy to
`documentation/history/RELEASE_NOTES_vX.Y.Z.md`, per `AGENTS.md`'s Release Checklist.

This file is a **template**. Every section below is either directly reusable as-is (marked *(reusable as-is)*) or a
scaffold to fill in for the specific project (marked *(fill in)*) — replace the bracketed guidance with the
project's own details and delete these template notes once done.

**Release Date:** {{Month DD, YYYY}} **Status:** ✨ Stable

---

## 🎯 Theme

*(fill in)* One short paragraph naming this release's overarching theme and why it matters.

---

## ⭐ Key Highlights

*(fill in)* The two or three most significant changes, each as its own `###`-level subsection with a short bullet
list — pick out what a reader skimming only this section needs to know.

---

## 📦 What's New

*(fill in)* Condensed from the matching `CHANGELOG.md` entry's categories (`Added`/`Changed`/`Fixed`/etc.),
high-level rather than exhaustive.

---

## 🚀 Migration Guide

*(fill in, if applicable)* Anything an API consumer or upgrading developer needs to change — omit this section
entirely if there's nothing to migrate.

---

## 📊 Statistics

*(fill in)* From `git log`/`git diff --stat` against the previous release, e.g.:

- **Total Commits:** {{count}}
- **Files Changed:** {{count}}
- **Insertions:** {{count}} lines
- **Deletions:** {{count}} lines

---

## 🧭 Design Notes

*(fill in, if applicable)* Notable design decisions this release made and why, framed as reusable rationale rather
than a changelog restatement.

---

## 🧪 Testing

*(fill in)* What was verified — test suite results, coverage, manual checks.

---

## 🐛 Known Issues

*(fill in, if applicable)* Carry forward any still-open issue from the previous release's Known Issues section that
this release didn't resolve.

---

## 🔮 Future Enhancements

*(fill in, if applicable)* What's planned next, building on this release.

---

## 👥 Contributors

*(fill in)* Sourced from actual git/GitHub history — run `git log --format='%an <%ae>' | sort -u`, scoped to this
release, per `AGENTS.md`'s Contributors convention. Never assume or guess who contributed.

---

## 📝 Notes

*(fill in, if applicable)* Anything else worth calling out that doesn't fit the sections above.

---

**For detailed change history, see [CHANGELOG.md](CHANGELOG.md)**

**For previous releases, see the [history folder](documentation/history)**
