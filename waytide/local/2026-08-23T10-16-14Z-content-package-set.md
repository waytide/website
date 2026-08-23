# Package set — content

- **Package set:** content
- **Packages:** foundation, git, journal, language, versioning
- **Inactive:** design-by-efferent, testing, tools/ruby-lang

## Why this set

**This project's product is prose and pages.** It is a Hugo site with the Hextra theme. What is
written here is articles, documentation, and the material of a site, and the conventions that
govern how that is written are the ones this set keeps.

**Design By Efferent is deactivated.** Its five hinges — actuation, observation, controls,
implementation, and naming — are a design method for a unit of code. An article has no actuation,
no observation of an effect, and no controls. Running the loop over prose would be the ceremony the
method exists to discontinue, reached from the other side.

**Testing is deactivated with it.** Its conventions are for writing tests, and Design By Efferent
is what asks for them.

**`tools/ruby-lang` is deactivated.** It is installed because it was placed here in the
2026-08-19 refresh, and this project builds no Ruby. A tool package is inert in a project that does
not use the tool.

## What this does not do

**Nothing is uninstalled.** All eight packages stay on disk and are refreshed as before. A
deactivated package's rules are read at session start exactly as an active package's are — the
declaration governs which are applied, not which are read.

**Taking one back up is a new declaration**, not a reinstall. The record with the latest time
prefix is the one that holds.

Related:

- the foundation a-project-declares-its-package-set rule — the mechanism, and what these three
  lines mean

---

Authored by Scott Bellware on Sun Aug 23 2026 at 3:16:14 AM PT
