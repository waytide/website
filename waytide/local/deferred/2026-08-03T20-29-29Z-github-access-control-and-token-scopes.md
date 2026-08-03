# Settle how this project authenticates to GitHub, and whether SSH is the right answer

Pushing `.github/workflows/hugo.yaml` was refused: GitHub requires the **`workflow`** scope to
create or update anything under `.github/workflows/`, and the token in use carries only `repo`,
`delete:packages`, and `write:packages`. The remote was switched to SSH, which pushes fine. That
resolved the immediate obstruction and **did not answer the question**.

**Gated on:** nothing in the work. It is actionable now, and was deferred deliberately — the
developer has no strict need for it yet and wants to understand GitHub's access-control model
before deciding.

## What is actually unresolved

**SSH does not satisfy the check; it steps outside the mechanism that performs it.** Scopes are
an OAuth and personal-access-token concept, and SSH key authentication is account-level access
with no scope model applied to it. So the protection was routed around rather than met. That is
defensible here — the account, the repository, and the workflow are all the developer's, and the
workflow is four screenfuls of Hugo build and Pages deploy — but it is a different thing from
having decided how this project should authenticate.

**Why the scope exists**, which is the part worth understanding before choosing: a file under
`.github/workflows/` is not inert content. It is code GitHub executes, on its own infrastructure,
on whatever trigger it declares, with access to repository and organization secrets, a
`GITHUB_TOKEN` whose permissions the workflow file itself requests, and the runners. A token that
could write workflows without saying so could turn a code-write credential into a secrets-read
one. The separate grant forces that to be an explicit decision.

## The current state, so it need not be reconstructed

- **`website`** — `origin` is `git@github.com:waytide/website.git`. Created by `gh repo create` as
  HTTPS; switched to SSH on 2026-08-03. Three pushes went over HTTPS before the switch.
- **`waytide`** (the composite) — `origin` is still
  `https://github.com/waytide/waytide.git`, untouched. It would hit the same refusal if a
  workflow file were ever added there under this token.
- **The token** comes from the `GITHUB_TOKEN` environment variable, so `gh auth refresh` will not
  change it — a token supplied that way is not one `gh` manages. Adding a scope means issuing a
  new personal access token and updating the variable.
- **`gh` separately reports a missing `read:org` scope**, unrelated to this and not investigated.

## The options, as they stood

- **Add the `workflow` scope** to the token and push over HTTPS. Meets the check rather than
  bypassing it.
- **Keep SSH.** Works, and is not subject to the scope model at all.
- **Push without the workflow** and add it through GitHub's web editor, which is not subject to
  the restriction.

**Why:** the immediate obstruction is gone, so nothing forces a decision — which is exactly how a
credential arrangement ends up settled by accident. What is in place now was chosen to get one
push through, not chosen as this project's answer, and the difference should be recorded rather
than left to look deliberate.

**How to apply:** when taking this up, decide whether this project authenticates to GitHub by SSH
or by a scoped token, apply the same answer to the composite repository, and record the decision
in the log. If a token is chosen, issue it with `workflow` and update `GITHUB_TOKEN`. Then delete
this item.

---

Authored by Scott Bellware on Mon Aug 3 2026 at 1:29:29 PM PT
