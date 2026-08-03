# A design can fall behind its own decision log, and nothing detects it

**Status:** a working hypothesis under discovery, not binding. It would be promoted to a rule if
a check can be stated that a person or an agent could actually apply — the gap is easy to
describe and, so far, has no proposed detection.

A decision is made, a log entry records it, and the **design the decision governs is never
updated**. The log and the design then disagree, and nothing in the system notices: the log is
append-only and correct, the design is internally coherent, and neither refers to the other in a
way that could be checked.

## What produced it

On 2026-08-03 the Human-Agent Relations tagline was settled and recorded in the composite
repository's log at `06:40:00Z` and `06:40:10Z`. It was **not** written into
*Waytide's Self-Explanation — Design*, which is where the website's formulations live. Five
minutes later, at `06:45:04Z`, that design was copied into the `website` project as part of the
planned content move. The copy was faithful. The material was simply not there to copy.

It surfaced later, when the tagline was applied to the site and someone went looking for its
reasoning. It was reconstructed from the two log entries.

## Why it went unnoticed, and why it was then misdiagnosed

**Nothing was wrong with any single artifact.** The log entries were accurate. The design was
consistent. The copy matched its source. A reader auditing any one of them would have found
nothing.

**The gap was then attributed to the move**, in a log entry claiming the material had been added
to the design after the copy and deleted in the reduction. Git contradicts both halves: the
composite's design has zero mentions of the material at every commit touching it, before the
copy, after the reduction, and now. The misdiagnosis is itself informative — a divergence between
a log and a design **looks like** a transfer failure, because a transfer is a discrete event with
a plausible culprit, where falling behind is a non-event with none.

## Why it matters here in particular

This project's designs are written against **drift** — a website describing a system that has
moved underneath it — and the answer settled for it is that both surfaces are produced from a
projection rather than authored. That answers drift between a **system and its description**. It
does not answer drift between **two of the system's own records**, which is what this is, and
which occurred inside the very design that argues against drift.

## What would promote it

A check that could actually be applied. Candidates, none satisfying:

- **A design names the log entries it rests on.** Makes the link checkable, and adds a
  maintenance burden to every design and every decision.
- **A decision names the design it changes.** Cheaper, since a log entry is written once and never
  revised — but nothing then verifies the design was actually updated.
- **A periodic reconciliation.** The work-sessions-convention already prompts a design
  reconciliation when a session record is written, which is the nearest existing mechanism. It
  fires only when a session record is written, and this decision was made in a session that
  produced none.

**Why:** a rule that names a gap without giving a way to detect it is ceremony — the failure this
system names most often. Better to hold the observation until the check exists than to canonize
an instruction to be careful.

---

Authored by Scott Bellware on Mon Aug 3 2026 at 2:29:53 PM PT
