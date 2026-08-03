# Feature — Hugo and Hextra Setup

## Intent

Stand up static site generation for the Waytide website with **Hugo** and the **Hextra** theme,
so the project has a real site to fill. The design settles the stack and the near-term shape —
Hextra's own demonstration site — and this feature is the work of putting it in place.

What it does **not** cover is what fills the site. That is content, produced from the projection,
and it is open in the design.

## Setup

- **State:** Completed
- **Upstream branch:** `master`
- **Feature branch:** `feature/hugo-hextra-setup`
- **Base:** `51937058e4c2f89767f0f6a6951cefc4a52ecee0` — `master`, *The near-term site reflects
  Hextra's demonstration site*
- **Working location:** branch only, chosen at initiation 2026-08-03. This working tree switches
  to `feature/hugo-hextra-setup` and switches back to `master` at the conclusion.
- **Loop record:** `waytide/local/loops/2026-08-03T18-17-31Z-hugo-hextra-setup.md`
- **Source design:** *Producing and Presenting Waytide's Self-Explanation — Design*,
  `waytide/local/design/2026-08-03T06-45-04Z-producing-and-presenting-waytide-self-explanation.md`

## Confirmations

- **2026-08-03 — Working location: branch only.** Put through the selection UI at initiation.
  Three options were offered — branch only, branch and worktree, and the current branch. The
  developer chose a branch and **named it**, `feature/hugo-hextra`, in place of the
  `feature/site-generation` that was proposed. The proposed name had been chosen to name the
  capability rather than the tools; the developer's names the tools.
- **2026-08-03 — Gating cadence: attended.** Put through the selection UI at initiation beside
  the working location. The loop stops at every hinge.
- **2026-08-03 — Completed, and the branch deleted.** The developer instructed both directly:
  *"mark the feature completed and delete the branch."* The lifecycle requires explicit
  confirmation before a branch is deleted, local or remote, and the instruction is that
  confirmation — it is recorded here rather than put back to the developer as a question they had
  just answered. **Both the local and the remote branch were deleted**, read as the ordinary
  meaning of the instruction after a merge; the branch was fully merged into `master`, so every
  commit remains reachable and nothing was made unrecoverable.

  **The remote branch was deleted under its pre-rename name, `feature/hugo-hextra`.** The rename
  moved the local branch and both records but was **never pushed**, so the remote kept the
  original name at commit `112ade8` while the local branch went on to `37e5fc0`. Two failures
  followed from it and are worth recording rather than tidying away: deleting
  `feature/hugo-hextra-setup` on the remote failed because no such ref existed there, and
  deleting the local branch was refused because git compared it against its stale upstream —
  `origin/feature/hugo-hextra` — and found it not merged *there*, even while reporting it merged
  to `HEAD`.

  **The local delete was then forced**, with `-D` rather than `-d`. That was done only after
  confirming containment directly: `git merge-base --is-ancestor` established that the remote
  tip was an ancestor of `master`, and the local tip `37e5fc0` likewise. The force overrode a
  check made stale by the unpushed rename, not the check's substance.
- **2026-08-03 — Renamed to `hugo-hextra-setup`**, at the developer's instruction, immediately
  before the merge. The branch, this record, and the loop record all moved with it. The name at
  initiation was `hugo-hextra`; the addition of *setup* narrows what the feature claims to have
  done — standing the tooling up, rather than Hugo and Hextra as a subject — which is what the
  intent above already says.

## Notes

**Neither Hugo nor Go is installed on the machine** as of initiation. Hextra requires the
**extended** edition of Hugo for either installation method, and the Hugo Modules method requires
Go as well. So the feature involves a change outside this repository, and the installation-method
hinge decides whether one tool or two are installed. **Resolved:** Hugo v0.153.3+extended was
installed with Homebrew; Go was not needed, the theme having come in by subtree.

## Conclusion

**Completed 2026-08-03.** Integrated into `master` as a **fast-forward** — `master` was a strict
ancestor, so the seventeen commits read in sequence with no merge commit. The build was verified
before the merge and again on `master`: 11 pages, no warnings.

**The first deployment ran and succeeded**, both jobs, and **the site is live at
`http://waytide.ai`** — serving the tagline, the claim line, the navigation, and `/docs/`. The
workflow, the action versions, the pinned Hugo, and the subtree-vendored theme all held up in CI
exactly as they had locally.

**What is not finished, and is deliberately not held against completion:**

- **HTTPS is not enforced.** GitHub has issued no certificate for the domain yet — the site
  presents GitHub's own `*.github.io` wildcard, so `https://waytide.ai` fails rather than warns.
  DNS first resolved minutes before the merge, and provisioning takes from a few minutes to about
  an hour. This is a wait, not a defect, and nothing in the repository changes when it clears.
- **The site is nearly bare.** A hero and one placeholder documentation page. That is by design:
  what fills the site is content, and the content areas are accumulating in their own design.

**A feature completes when its intent is built and integrated**, and the intent was standing the
tooling up. Both remaining items are downstream of that rather than part of it.

## Outstanding dependency — DNS — resolved

**`waytide.ai` does not resolve to GitHub Pages, and this feature cannot make it.** The domain is
on registrar parking — an `A` record to `192.64.119.231`, and `www` to
`parkingpage.namecheap.com` — with nameservers at `dns1`/`dns2.registrar-servers.com`. The
records GitHub documents for an apex domain have to replace it:

- **A** `@` → `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
- **AAAA** `@` → `2606:50c0:8000::153`, `2606:50c0:8001::153`, `2606:50c0:8002::153`,
  `2606:50c0:8003::153`
- **CNAME** `www` → `waytide.github.io`

The existing parking records for `@` and `www` conflict and have to be removed.

**Two consequences.** **HTTPS cannot be enforced** until the domain resolves — GitHub issues the
certificate only then, and the Pages API currently reports `https_enforced: false` with the URL
as `http://waytide.ai/`. And **a deploy will succeed while the site stays unreachable at its own
address**, which is the state to expect between the merge and the DNS change.

**This is outside the repository and outside the agent's reach.** It was recorded here so that
concluding the feature would not read as the site being live.

**Resolved 2026-08-03, by the developer, before the merge.** The apex now answers with all four
GitHub addresses and all four IPv6 addresses, `www` is a CNAME to `waytide.github.io`, and the
five `MX` records and the SPF `TXT` survived intact — which was the hazard worth naming, since
losing them stops mail silently. The order turned out to be DNS first and the merge second, the
reverse of what the paragraph above anticipated, so the site was reachable at its own address the
moment the first deployment finished.

---

Authored by Scott Bellware on Mon Aug 3 2026 at 11:17:31 AM PT
Changed by Scott Bellware on Mon Aug 3 2026 at 2:01:00 PM PT
Changed by Scott Bellware on Mon Aug 3 2026 at 2:16:43 PM PT
Changed by Scott Bellware on Mon Aug 3 2026 at 2:19:41 PM PT
Changed by Scott Bellware on Mon Aug 3 2026 at 2:21:34 PM PT
