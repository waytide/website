# Producing and Presenting Waytide's Self-Explanation — Design

## Summary

This design settles **how Waytide's self-explanation is produced and how it is presented** — the
two surfaces it reaches people through, the projection both are produced from, the constraint
distribution places on that source, the shape of the website's home page, and the points the
website should make.

**The reasoning behind it stays in the composite repository.** Why Waytide explains itself at
all, what prompted the design, and the terms it rests on remain in *Waytide's Self-Explanation —
Design*, at `waytide/local/design/2026-08-03T00-45-18Z-waytide-self-explanation.md` in the
composite authoring repository (`waytide`). That design and this one were one artifact until
2026-08-03; the division is recorded in the composite's migration record *The website content
moves to its own project*.

**Two resolutions are inherited from it** and are not re-settled here, since they are the premise
this design proceeds from:

- Waytide explains itself through an **interactive chat with the agent**, skewed toward
  explaining the system rather than the developer's project (settled 2026-08-02).
- **The website's content is driven by that same content.** One source, two surfaces; not two
  separately-maintained explanations (settled 2026-08-02).

**What this design does not settle is the mechanism that makes the explanation repeatable** —
how a request for an explanation is taken, normalized, and recorded, so that a projection is
produced again rather than assembled once by hand. That is this project's own forward work and
is named under Out of Scope / Deferred.

## Vocabulary

The terms are defined and argued in the composite's design; they are glossed here so this
document reads on its own.

- **Surface** — a place a user meets the explanation. There are two: the interactive chat, and
  the website.
- **Source** — what both surfaces are produced from. Not itself a surface.
- **Skewed toward explaining itself** — the chat answers about **Waytide** rather than about the
  developer's project, which is what an agent in a consuming project ordinarily does.
- **Projection** — a derived artifact generated from the records the system already keeps, in
  the sense the decision-log convention already uses, where a summary "reads the record without
  destroying it". Derived rather than authored, and regenerable rather than fixed.

## The two surfaces

**The chat** is interactive and agent-produced. Its distinctive capability is that it answers a
question the explanation's author did not anticipate — the thing no document can do.

**The website** is static and public. Its distinctive capability is reaching someone who has
installed nothing and is deciding whether to.

They are not the same artifact and cannot be. **A website cannot be a chat**, so what they
share is a **source**, not an output.

## The source is a projection

**Settled 2026-08-03.** Both surfaces are produced from a **projection** — a derived artifact
generated from the records the system already keeps, rather than from prose written to explain.
The chat draws on it; the website is generated from it.

**What that means, and what it rules out.** Two other candidates were weighed:

- **The rules themselves.** Nothing could drift, because nothing would sit between the rules and
  either surface. But rules are written to **govern**, not to introduce: a reader meeting the
  system needs an entry path and the reasoning behind the shape, and no individual rule states
  either.
- **A written corpus.** Prose written to explain, which the chat draws on and the site
  publishes. It reads as an introduction and can carry the reasoning — and it is exactly the
  artifact that **drifts**. The composite repository has that failure documented three times over
  in its own package READMEs, which are hand-maintained descriptions of what the rules say and
  were corrected by hand when the rules moved underneath them.

**A projection is neither.** It is **derived rather than authored**, so nothing is maintained
alongside the system that can fall out of step with it; and **regenerable rather than fixed**,
so when the system changes, the explanation is produced again rather than corrected. That is
precisely the property a written corpus cannot have and the reason a written corpus drifts.

**It is the same mechanism the Constant example project design settles for the replay** —
`constant`'s logs are not read literally; an idealized log is generated, the Waytide cycles and
steps are synthesized from it, and a website script is sequenced and generated from that. This
design adopts the mechanism for the whole of the explanation rather than the home page alone.
See *The Constant Example Project — Design*, which stays in the composite repository at
`waytide/local/design/2026-08-03T05-40-22Z-the-constant-example-project.md`.

**What a projection does not excuse.** It is derived, not automatic — something decides what is
included, in what order, and at what altitude. Two constraints already settled for the replay
carry to every projected surface:

- **It must not present as something it is not.** A projected explanation is not a transcript,
  not a recording, and not the rules themselves, and what it derives from must be reachable.
- **The records are not back-edited to suit it.** A projection is derived from a record; changing
  the record to fit the projection destroys what makes the projection worth anything.

**The open question moves rather than closing.** What "idealized" is allowed to change is this
design's question as well as the Constant design's, because it decides whether every surface is
trustworthy and not only the home page. Compressing, omitting, and inventing are not the same
act.

## The distribution constraint

Anything a user reads **in their own project** must live in a package: `git subtree` carries
only package directories, which is the same constraint that put the consuming-project tooling
in `foundation`. So a written source is not free to live anywhere — it goes in a package, and
`foundation` is the only one always installed.

A source consulted only by the website has no such constraint, but a source serving both does.

**This bears directly on where this project's rules can reach.** Rules held in this repository
govern the work done here — producing the projection. They do not reach an agent running in a
developer's own project, which is where the chat surface runs. See Out of Scope / Deferred.

## The near-term site

**The site reflects Hextra's own demonstration site**, at `https://imfing.github.io/hextra/`.
That is what the website is until the home page described below is reached.

**The shape that site presents**, as of 2026-08-03: a hero carrying a headline, a tagline, and a
single call to action; a row of feature cards beneath it; and top navigation dividing the site
into documentation, a blog, and a showcase. Full-text search, a light and dark theme toggle, and
multi-language support are part of what the theme supplies rather than things to be built.

**It is the theme's own demonstration, which means the theme is used substantially as it comes.**
That is what makes it reachable soon: the work is filling a shape rather than making one.

**What it settles and what it leaves open.** It settles the site's **shape and presentation**. It
does not settle **what fills it** — what the documentation says, whether there is a blog, what a
showcase would show. That content comes from the projection, like every other surface.

**It differs in kind from the home page below, and the two are not versions of one thing.** A
demonstration site's shape is a documentation site: sections, navigation, search — a reader
chooses where to go. The home page is a single rendered session on one continuous scroll, where
the reader goes one way and the length is part of the argument. Reaching the second is not a
restyling of the first, and a plan should not treat it as one.

## The home page

**Everything in this section is a long-horizon aspiration, not the near-term build.** The page
described below — the two vertical sides, the expandable summaries, the scroll that goes on and
on — is where the home page is meant to arrive, and it is settled as **direction** rather than as
the next thing built. It is stated here at the top because every resolution in this section reads
as a commitment otherwise, and a plan drawn from it would sequence work nobody intends to start
yet.

**What the site is in the meantime is not settled anywhere**, and that gap is named in Out of
Scope / Deferred. Recording the aspiration without recording that it is one would leave the
design describing a site that is not being built, which is the drift failure arriving from the
inside.

**The distinction is horizon, not confidence.** Nothing below is tentative — the shape was
reasoned through and settled. What is deferred is when it is reached.

**The website is not itself an interactive chat.** The chat on the page is a **content and
style element** — a rendered scroll of a **synthesized session**, not something the reader
converses with. The interactive chat is the other surface: the agent, in a developer's own
project. The two share a source; they are not the same artifact, and the page does not pretend
to be the product.

**The page's structure:**

- **A top header and a short hero image.**
- **Below it, two vertical sides.** On the **left**, the chat. On the **right**, **what the
  agent touched** — both the **sources consulted** to answer a request and the **artifacts
  created** by the work, each appearing at the point in the session it belongs to.
- **Each entry is an expandable summary**, clickable to open the record, the file, or the query
  in full.
- **It can scroll on and on**, an infinite scroll through the synthesized session with the
  `constant` library.

**The right side carries both directions, and that is the point.** Work under this system both
**reads** and **writes**, and the right pane shows each at the moment it happens:

- **Sources consulted.** When a request is made — a test report, a status report, a deferred
  listing, anything — the queries and the files read appear on the right. Every answer on the
  left has its provenance beside it.
- **Artifacts created.** Log entries, loop records, feature records, appearing at the exchange
  that produced them.

**Showing the sources answers a question about the whole system that prose cannot.** The rules
require that reports be **re-derived from current files rather than recalled** —
`status-report-format` says "do not report stale task counts, suite numbers, contexts, or
deferred items from memory," and `test-report-format` says "re-derive everything from the
current files." Those are promises. A reader watching the files being read beside the answer
being given sees the promise kept, and gets a structural answer to the question every reader of
an AI system has: **whether any of this is grounded or invented.**

**Showing the artifacts makes the other central claim visible.** Working this way **accumulates
a record** — committed alongside the code. Prose can assert that. A reader watching a log entry
appear beside the exchange that produced it sees **when** it is written, which is the part a
description always leaves vague.

**The summaries are collapsed by default and expand on demand** because the two sides are doing
different work. The chat carries the reader forward; the artifacts show what it left behind. An
artifact opened in full stops the forward motion, which should be the reader's choice and not
the page's.

**Navigation appears when the reader begins to scroll.** It is absent on arrival, so what is on
screen first is the hero and the chat coming up beneath it, with nothing competing.

**Why a rendered session rather than a description.** Every other way of introducing the system
says what it is. A session showing a whole process shows **what using it is like** — the questions a
developer actually asks, the points where the system stops and asks back, what the artifacts
look like as they accumulate. That is not a claim about the system that a reader has to take on
trust; it is the thing itself, and its length is part of what it demonstrates. A short excerpt
would show the surface and hide the process, which is exactly what is worth showing.

**The length is deliberate and is the design.** A reader who scrolls a long way has seen a
real working session rather than a pitch, and one who scrolls a little has still seen more of
the method than a features list would give them.

**It is loosely scripted — just the bones.** Not a raw session transcript, and not written
prose in the shape of one. The **sequence** is scripted; what happens inside each step is the
system doing what it does. That keeps the two properties that matter in tension: a reader sees
a real working session rather than a composed argument, and the session still gets somewhere
rather than wandering as a real one would.

**The opening sequence:**

1. **`git` install** — the packages installed into a project.
2. **`load waytide`** — the rules read, closing with the deferred queue printed.
3. **Starting a feature** — initiation, with the working-location and attended-or-unattended
   choices put to the developer.

Every step is a real, rule-governed moment rather than a demonstration written for the page,
and the last is where the method's distinctive behavior shows: it puts **selections** to the
developer rather than proceeding, which is the thing a features list cannot convey.

**A status report is deliberately not in the opening sequence.** It was considered and dropped:
at project initiation there is no plan, no deferred queue, no decision log, and no suite, so
the report would print its shape with nothing in it. A form with no content demonstrates the
form, which is the least interesting thing the system does, and it would spend the reader's
first minutes on emptiness. The status report belongs where there is something to report.

**One residue of that.** The deferred-queue print at step 2 has the same problem in miniature —
on a fresh install it says the queue is empty. It is one line rather than a section, and it
shows that the queue is reported at all, so it stays.

**`constant` is the source material for the transcript.** It is a real project built under
Waytide throughout, and its artifacts are the bones a loosely-scripted session would be
assembled from — a record of work that actually happened, which is precisely what a written
session cannot be. What is there, as of 2026-08-03:

| Artifact | Count |
|---|---|
| decision log entries | 206 |
| loop records | 19 |
| feature records | 6 |
| work-session records | 5 |
| observations | 11 |
| experiments, plans, designs | 2 each |
| the project's own local rules | 3 |

**Three features carry both a feature record and a loop record**, which is what a transcript
needs — the lifecycle from the one, the design cycles from the other:

- **`import-literal-constants`** — 6 cycles. Short enough to follow end to end.
- **`import-shadow-inherited`** — 7 cycles, and the feature was later renamed
  `override_ancestor`. It therefore shows a **terminology correction landing on finished work**,
  which is a real and unflattering part of the method that a composed example would omit.
- **`import-collision-refusal`** — 19 cycles. The fullest record and almost certainly too long
  for a home page, though it is the best evidence that the method is actually run.

The work-session records are the other candidate: each already narrates an arc, which is close
to what the page wants, and they point at the durable records rather than restating them.

**This is the same property the Constant example project has**, on a different surface: its
value is that the process is exhibited rather than described. Whether the home-page chat draws
on that project is not settled — though it is the same body of artifacts already named above as
the transcript's source material, which makes the two questions nearly one.

## Package Dependency

**The site is generated with Hugo**, a static site generator, **and Hextra**, a Hugo theme.

**The choice is an opportunity as much as a fit, and it is recorded that way rather than dressed
up.** This project is being used as the occasion to exercise static site generation with Hugo and
Hextra. Presenting the stack as the conclusion of a comparison nobody ran would misdescribe how it
was arrived at, and a design that misdescribes its own reasoning is the kind of drift this design
exists to prevent — arriving from the inside rather than from a public page.

**What it settles, and what it does not.** It answers what **builds** the site. It does not
answer what **feeds** the build: the projection has to reach Hugo in some form, and which records
produce it is open. The one-way flow requirement is untouched — whatever assembles the input,
nothing flows back from the site into the records it was derived from.

**Where the choice would eventually show a cost — but not soon.** The home page as designed
makes demands unusual for a theme built around documentation pages: two vertical panes tracking
one scroll, a per-entry expandable summary on the right, and a page long enough that its length
is part of what it demonstrates. Those are the parts most likely to strain the theme.

**That strain is deferred with the page itself.** The home page is a long-horizon aspiration
rather than the near-term build, and the near-term site reflects **Hextra's own demonstration
site** — the theme carrying exactly what it was built to carry. So the demands above are not what
Hextra has to answer first, and they are not a reason to weigh the stack differently now. It is recorded so that the question is already on the
page when the aspiration is taken up — at which point the theme either carries it, is extended,
or is the thing that has to change.

## Points the website should make

A running collection, added to as points surface. Each entry is a point worth making publicly
and the reason it is worth making, not copy.

- **The cycle is chosen, not performed.** DBE rejects red-green-refactor **as choreography** —
  the cycle nobody decided to run — and not as a choice. At the implementation hinge the
  developer is offered two candidates: the working implementation, or the red/green/refactor
  cycle. Selecting the cycle for a particular unit is a design judgment, which is the opposite
  of ceremony.

  **Why it belongs on the website.** A reader who knows TDD arrives with one of two
  assumptions — that this is TDD with extra apparatus, or that it is against TDD. It is
  neither, and this is the shortest thing that shows why: the cycle is available and *chosen*
  rather than *performed*. It also demonstrates the method's general shape in miniature — a
  subtle, load-bearing decision put to a person instead of settled by a procedure — which is
  the thing hardest to convey by describing it.

- **The developer chooses at every gate; the work goes where they take it.** Nothing about a
  session is fixed in advance. The working location, the gating cadence, each hinge's
  resolution, whether a unit is driven through the cycle, what the next outcome is — all of it
  is put to the developer and none of it is decided by the agent. The path through a piece of
  work is the developer's, and a different set of choices produces a different piece of work.

  **Why it belongs on the website.** It is the single fact that most distinguishes this from
  tooling that automates a workflow, and it explains the apparatus rather than merely listing
  it: the hinges, the selection interface, the records of what was decided all exist because
  the choosing is the point. A reader who grasps this understands why the system stops as often
  as it does, which otherwise reads as friction.

  **A caution on how it is said.** "Choose-your-own-adventure" states it precisely and in one
  familiar phrase, and it is an analogy — which the `language` package's
  name-literally-not-by-analogy rule rejects for **naming a concept**, on the ground that the
  reader must learn and carry a mapping. Whether it is admissible as *website prose*, where a
  near-universal reference costs a reader nothing, is a real question and is not settled here.
  What the point itself claims does not depend on the phrase.

- **Five phrasings of the same stance, each foregrounding something different.** Kept together
  because each is accurate and they are not interchangeable — the one to use depends on what a
  passage is doing. The first is settled as the **rule's** name (see the composite's observation
  *"The developer chooses" is a cross-cutting stance that no rule names*); all five are here as
  ways of **characterizing** the system.

  - **The agent proposes; the developer decides.** States both roles and the division between
    them. Echoes the method's own spine, *"the AI generates; the human deliberates."* The one to
    use when explaining how a session actually runs.
  - **Nothing is decided by default.** States the negative the rules enforce, and it is drawn
    from their own words — "no standing default" is the recurring phrase at the working location
    and the gating cadence. The one to use against the assumption that a tool has opinions it
    applies silently.
  - **The agent does not decide for the developer.** The plain prohibition. The one to use when
    a reader's worry is what the agent will do while they are not looking.
  - **The work goes where the developer takes it.** The literal rendering of the
    choose-your-own-adventure sense, without the mapping. Describes the result rather than the
    mechanism, and is the most inviting of the five.
  - **Every decision that is the developer's is put to them.** The most exact, and the one that
    carries a **test** rather than a sentiment: *is this decision the developer's?* The one to
    use where a reader wants to know how the line is drawn.

  **Why they belong on the website.** The stance is the thing hardest to convey by listing
  features, and it is what a reader has to grasp for the apparatus to make sense rather than
  read as friction. Having five accurate phrasings means a passage can state it again without
  repeating itself, and each entry says what its phrasing is *for*.

- **"Waytide: Human-Agent Relations"** — **the tagline, settled 2026-08-03.** It names the
  **subject**: what the system governs is the relationship between a human and an agent — who is
  bound, who decides, where the gates fall. It matches how the packages are named, since
  `language`, `testing`, and `versioning` are subjects rather than claims.

  **It alludes to C-3PO's self-introduction**, *"I am C-3PO, human-cyborg relations"*, and that
  is the point of it for a technical reader. The allusion carries what the words alone would
  lose: **C-3PO is a protocol droid who never decides.** He advises, calculates the odds, and
  objects; Han does it anyway. That is the agent-proposes-the-human-decides stance, inside the
  reference.

  **It survives the naming standard where a metaphor would not.** `name-literally-not-by-analogy`
  rejects names that require the reader to learn a mapping. This one requires none — *Human-Agent
  Relations* describes the subject accurately to a reader who has never seen the film. The
  allusion is a **second layer**: it rewards catching it and costs nothing to miss, which is what
  distinguishes it from a metaphor, unintelligible until decoded. Recorded as an observation in
  the composite repository.

  **What it does not do is make a claim.** It says what Waytide is about, not what it does or
  whose side it is on, and the asymmetry is there only for readers who catch the reference. That
  is what the entry below is for.

- **"Waytide: The Human Ally Harness"** — the **claim** line, settled 2026-08-02 and
  **superseded as the tagline on 2026-08-03**. It is kept: it states what the system does and
  whose interest it serves, which the tagline does not, and a page wants both.

  **"Your agent, your ally. The agent proposes, you decide."** is the expanded form, settled
  2026-08-03 and carried on the landing page beneath the tagline.

  **It abandons the harness construction rather than repairing it.** Every earlier form turned on
  a verb claiming the harness *produced* an ally, and the objection that retired them was that
  such a verb is **presumptuous**: it promises a result the reader cannot check, and implies a
  transformation — the agent was not an ally, and now is, because of this. Weakening the verb
  would have softened the claim without removing its shape.

  **What replaces it is claim then grounds.** The possessives assert the relation without
  claiming anything produced it, and the second sentence immediately says what the relation
  consists of, so *ally* arrives with its evidence attached rather than asking to be taken on
  assurance. That is what the content-areas design requires of the word — that it be shown as
  something inspectable rather than asserted as a disposition.

  **The mechanism half is settled vocabulary**, not new: *the agent proposes; the developer
  decides* is the first of the five phrasings below and echoes the method's spine. The landing
  page says *you* rather than *the developer* because it addresses a reader directly.

  **It states the attended default**, which is what a first reader meets. Under unattended work —
  opt-in, and affirmed before the agent proceeds — the agent decides each hinge, so the line
  describes the cadence a reader begins in rather than the only one available.

  **A known risk in the compressed form, recorded rather than acted on.** English noun-stacks
  bind rightward, so *human ally harness* is available to a first-time reader as *a harness for
  human allies* — the compliance reading that "ally" was introduced to foreclose. The intended
  reading — a harness under which the agent stands as the human's ally — is the better claim and
  arrives on the second pass. The compression was chosen deliberately with this understood; the
  expanded form exists to carry the intended reading wherever the compressed one would be met
  cold.

  **This gloss is not a candidate wording.** It describes how the compressed form parses. Every
  phrasing that made the harness the *actor* — that it produced, kept, or let the agent be an
  ally — was retired on 2026-08-03 as presumptuous, and the gloss is worded to avoid reinstating
  one by the back door.

  **Waytide is an agent harness and a human ally** remains the definitional sentence, and what
  each half is for is settled below.

  **"Agent harness"** states the mechanism. The rules are **binding** on the agent — they
  "override default behavior where they conflict," and the agent has no discretion to depart
  from them. Note that `dbe-as-design-tool` rejected "harness" for the **cradle**, on the ground
  that a cradle must hold the implementation "without gripping it rigid." That objection does
  not carry here: gripping rigid is precisely what the agent's rules do, so the word fails for
  the test and holds for the agent.

  **"Human ally"** forecloses a reading the mechanical phrasings leave open. A system of
  rules, records, logs, and gates looks, from a distance, like **process compliance imposed on
  the human** — surveillance and metrics have that shape. Saying the human is allied with
  answers that immediately, and no statement of authority does: *binds the agent and defers to
  the human* says who decides without saying whose interest the apparatus serves.

  **"Human" rather than "engineer", settled 2026-08-02.** It is the pairing the method's own
  lexicon uses — `design-by-efferent` says *human* 111 times, in *human-in-the-loop* and in "the
  AI generates; the human deliberates" — and it is the only one that pairs correctly with
  *agent*, which names a kind of entity rather than a role. *Engineer* appears nine times across
  three files and is the least established of the three words the system uses for this party.
  **The known risk is register:** "human ally" is close to AI-marketing idiom, and it lands in
  the sentence that introduces the system. It is accepted deliberately; the pairing was judged
  worth it.

  **One thing the pair does not say, which may want a second sentence.** The two halves are not
  symmetrical, and the parallel invites reading them as though they were. The engineer is
  constrained too — branch topology, record contents, commit wording, when a decision is logged.
  What distinguishes the parties is not constraint against support: **the agent is bound and
  given no discretion; the human is bound and given all of it.** "Harness" states a
  mechanism, "ally" states a disposition, and the second does not follow from the first.

## Settled

Each resolution keeps the date it was settled on. Those dated before 2026-08-03 were settled in
the composite's design, before this one was divided from it.

- **2026-08-02** — **The initial interaction design parameters are the developer's** and are
  given rather than inferred. The work starts from them.
- **2026-08-03** — The two surfaces share a **source**, not an output, since a website cannot be
  a conversation.
- **2026-08-03** — **The source is a projection** — derived rather than authored, regenerable
  rather than maintained. The rules alone and a written corpus were both weighed and rejected:
  the rules govern rather than introduce, and a corpus is the artifact that drifts. The two
  constraints settled for the replay carry to every projected surface — it must not present as
  something it is not, and records are not back-edited to suit it.
- **2026-08-03** — **The home page is a very lengthy chat with Waytide** describing a whole
  process of using it, on one continuous scroll.
- **2026-08-03** — **The website is not itself an interactive chat.** The chat on the page is a
  content and style element — a rendered scroll of a synthesized session. The interactive chat
  is the other surface.
- **2026-08-03** — **The page is a top header and a short hero image, with the chat below it**,
  scrolling into view and continuing through the synthesized `constant` session.
- **2026-08-03** — **The scroll has two vertical sides: the chat on the left, and on the right
  what the agent touched** — the **sources consulted** for any request, and the **artifacts
  created** by the work. Each is an expandable summary, clickable to open in full.
- **2026-08-03** — **Navigation appears when the reader begins to scroll**, and is absent on
  arrival.
- **2026-08-03** — The transcript is **loosely scripted — just the bones**. The sequence is
  scripted; what happens inside each step is the system doing what it does.
- **2026-08-03** — The opening sequence is **git install → `load waytide` → starting a
  feature**. A status report was considered for the sequence and **dropped**: at initiation
  there is nothing to report, and a form with no content demonstrates only the form.
- **2026-08-03** — **The site is published at `waytide.ai`**, a domain the project owns. It is
  the site's address in `hugo.yaml`, replacing the GitHub Pages address that stood there
  provisionally. Where the domain points — what hosts the built site — is a separate question and
  is open.
- **2026-08-03** — **The near-term site reflects Hextra's own demonstration site**, at
  `https://imfing.github.io/hextra/` — a hero with a headline, tagline, and one call to action;
  feature cards; and navigation dividing documentation, a blog, and a showcase, with search and a
  dark theme supplied by the theme. It settles the site's shape and presentation, not what fills
  it, and it is a documentation site rather than a smaller version of the home page below.
- **2026-08-03** — **The home page described here is a long-horizon aspiration**, settled as
  direction rather than as the next thing built. Every home-page resolution below is read that
  way: the shape is not tentative, but when it is reached is deferred. What the site is in the
  meantime is not settled.
- **2026-08-03** — **The site is generated with Hugo and the Hextra theme.** This project is the
  occasion to exercise static site generation with that stack, which is part of the reason for the
  choice rather than only its technical fit. It settles what builds the site, not what feeds it.
- **2026-08-03** — **This design holds the operational half of Waytide's self-explanation** —
  the two surfaces, the projection, the distribution constraint, the home page, and the points
  the website should make. The composite's design keeps the reasoning: why Waytide explains
  itself, what prompted it, and the vocabulary. The alternative weighed was moving the design
  whole and leaving a stub in the composite.
- **2026-08-03** — **The tagline is "Waytide: Human-Agent Relations."** It names the subject
  rather than making a claim, and alludes to C-3PO's self-introduction, which carries the
  agent-proposes-the-human-decides stance inside the reference. *"Waytide: The Human Ally
  Harness"* is superseded as the tagline and kept as the claim line.
- **2026-08-03** — **The rules that query, normalize, and record explanation requests are this
  project's own local rules**, under `waytide/local/rules/` with the ISO-8601-UTC filename
  prefix. Whether they are later promoted into a distributed package is left open.

## Out of Scope / Deferred

- **How a request for an explanation is queried, normalized, and recorded.** This is the
  project's own forward work and the reason the material moved here: a projection is worth
  having only if it can be produced again, and nothing yet says what an explanation request is
  taken to be, how it is normalized into a form the projection answers, or what is recorded of
  it. Not settled anywhere.
- **Whether those rules are promoted into a distributed package.** They are local for now. The
  distribution constraint decides the question: rules held here govern the work done here and
  cannot reach an agent running in a developer's own project, which is where the chat surface
  runs. If the chat surface is to be governed, the rules have to be installed with a project.
- **What "idealized" is allowed to change** — shared with the Constant example project design.
  Compressing a long cycle, omitting a false start, and inventing a decision nobody made are not
  the same act, and nothing yet says where the line falls.
- **The interaction design parameters** — how the chat opens, what it offers, how far it leads
  versus follows. To be provided by the developer.
- **What makes the chat lean toward the system** — a command that opens it, a mode it stays in,
  or a rule about which question it takes as asked. Part of the interaction design.
- **What the projection is generated *from*, beyond the replay** — the rules are the obvious
  input for what each package governs, but the reasoning behind the shape is not derivable from
  them and lives today in designs, observations, and session records. Which records feed which
  surface is not settled.
- **Whether anything written has to be installed with a project.** A projection produced for the
  website has no distribution constraint; one the chat draws on inside a consuming project does,
  since subtree carries only package directories.
- **Where the site is hosted, and how it is deployed.** The address is settled — `waytide.ai` —
  and what the domain points at is not. GitHub Pages, which the repository's home and Hextra's
  starter template both suggest, and Netlify, which the theme ships a configuration for, are the
  obvious candidates, and neither is chosen. The choice decides what else the repository carries:
  a `CNAME` file for Pages, a build workflow, or a host's own configuration.
- **What fills the near-term site.** Its shape is settled — Hextra's demonstration site — and its
  content is not. What the documentation says, whether there is a blog, what a showcase would
  show, and which of them the projection feeds are all open. This is the nearest-term question the
  design leaves, and the one a plan would hit first. **The content areas the site carries are
  accumulating** in *The Site's Content Areas — Design*, which begins to answer this without
  closing it: it says what the site covers, not how the coverage is produced or arranged.
- **How the near-term site becomes the home page**, given they are different kinds of page rather
  than two finishes of one. Whether the home page arrives as another page on the near-term site,
  replaces its landing page, or waits for a rebuild is not settled.
- **What feeds the generator.** Hugo and Hextra settle what builds the site; what produces their
  input does not follow from that. Whether the projection is generated at publish time from the
  packages, assembled from the component repositories, or produced some other way is open. The
  flow must be one-way, as composite → component already is.
- **Whether the removed website drafts return**, and in what form.
- **Whether the transcript replays a `constant` feature or is a new session run for the
  purpose** — **deferred to planning**, not settled here. Replaying has the property that it
  happened; running a new one can follow the settled opening sequence exactly, which none of the
  existing records do, since all six features were begun before that sequence existed. The
  choice depends on how the transcript is actually assembled, which is a plan's concern.
- **Where a status report appears later in the transcript**, once the project has a plan, a
  queue, and a log to report — or whether it appears at all.
- **What the feature at step 3 is**, and how far the transcript follows it — to its first gated
  hinge, or through to its conclusion.
- **What comes after the opening sequence**, which is scripted only to step 3.
- **How the scripting is kept honest.** Loosely scripted means the sequence is chosen and the
  content is not; nothing yet says what stops the content being tidied into a composed
  argument, which is the failure that would make the page a pitch after all.
- **What "one continuous scroll" requires of the implementation** — whether content loads as the
  reader scrolls or the page is simply long and unpaginated. Read here as the latter unless
  length forces otherwise.
- **What the navigation contains**, and whether it persists once shown.
- **How the two sides behave on a narrow screen**, where they cannot sit side by side.
- **Whether an artifact stays in view once it appears**, or scrolls away with the exchange that
  produced it. A record that persists shows accumulation; one that scrolls away shows sequence.
- **Which entries are shown, and how volume is handled.** A status report reads a great many
  files, and listing every one swamps the pane. The projection decides what appears — the same
  "what is idealized allowed to change" question, arriving on the right-hand side, where
  omitting a source is a stronger claim than omitting an artifact.
- **Whether reads and writes are distinguished**, and how. They are opposite directions and the
  pane now carries both.
- **What an artifact's collapsed summary contains** — its title alone, or its title and a line
  of what it says.
- **The plan that sequences this.** Not written; this design settles direction only.

---

Authored by Scott Bellware on Sun Aug 2 2026 at 11:45:04 PM PT
Changed by Scott Bellware on Mon Aug 3 2026 at 12:16:25 AM PT
Changed by Scott Bellware on Mon Aug 3 2026 at 12:19:26 AM PT
Changed by Scott Bellware on Mon Aug 3 2026 at 12:22:39 AM PT
Changed by Scott Bellware on Mon Aug 3 2026 at 12:37:27 PM PT
Changed by Scott Bellware on Mon Aug 3 2026 at 1:36:57 PM PT
Changed by Scott Bellware on Mon Aug 3 2026 at 1:45:59 PM PT
Changed by Scott Bellware on Mon Aug 3 2026 at 1:50:20 PM PT
Changed by Scott Bellware on Mon Aug 3 2026 at 1:52:59 PM PT
Changed by Scott Bellware on Mon Aug 3 2026 at 1:57:24 PM PT
