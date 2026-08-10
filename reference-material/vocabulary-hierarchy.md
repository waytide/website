# The Vocabulary Hierarchy

Waytide binds several vocabularies at once, and a word can appear in more than one. This states
the order they decide in, what sits at each level, and what a vocabulary holds. It is settled by
`foundation`'s vocabulary-convention rule, which is the authority — this page describes it.

**This file sits in `reference-material/` for now.** Its final place is not settled, and the
content-areas aspiration records how an area becomes a page as still open.

---

**The order, from the one that decides first.**

1. **The STE dictionary** — and Waytide's reserved terms where the approved word means something
   else. The `language` package's waytide-keeps-its-word-where-the-ste-word-means-something-else
   rule states this level and its exception.
2. **`language`'s vocabulary** — the terms and substitutions that belong to no domain.
3. **An individual package's vocabulary** — the terms and substitutions of one domain.
4. **The project's own vocabulary**, in `waytide/local/vocabulary.md`.

**The more specific decides.** A domain knows its own words, and a general vocabulary cannot
anticipate what a domain needs. A project knows its own work, and Waytide cannot anticipate that
either.

**What exists at each level:**

```
1  the STE dictionary          local/reference/ASD-STE100-issue-9-dictionary.txt
                               local/reference/ASD-STE100-issue-9-writing-rules.txt

2  language/vocabulary.md      terms · substitutions · design-vocabulary words

3  foundation/vocabulary.md    terms · substitutions · discontinuations
   design-by-efferent/         terms · substitutions · discontinuations
   testing/vocabulary.md       terms · substitutions
   versioning/vocabulary.md    terms

   git · code · code/ruby      no vocabulary — their domains have no specialized words

4  local/vocabulary.md         one file, no datetime prefix, optional
                               read at session start with the rules
```

**Specialization is not conflict.** A package may narrow a general term rather than displace it —
`language` defines `actuation` as the invocation of a unit from its use site, and
`design-by-efferent` keeps that and adds that the actuation is written before any implementation.
The narrower entry rests on the general one, and the entry says which case it is.

**A vocabulary holds four kinds of thing**: terms it defines, substitutions naming a word not to
write and the word to write instead, discontinuations naming a word taken out of use with nothing
in its place, and words taken from the established design vocabulary and used in their own sense.

**A package gets a vocabulary only where its domain has specialized words.** A package whose
subject is written in ordinary words has none, and the absence is correct rather than missing.

---

Authored by Scott Bellware on Mon Aug 10 2026 at 1:33:20 PM PT
