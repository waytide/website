# The Hinge Cycle — An Example Session

A worked demonstration of Design By Efferent's loop, written as a session a reader can follow
from the first request to a published gem. **It is a demonstration and not a record of work that
happened**, so it belongs in neither `waytide/local/loops/` nor any other record directory. The
retry count, the client, and the version numbers are invented.

It shows the five hinges as a reader meets them: the account given once ahead of the first hinge,
each hinge presented through the selection interface with its candidates written as the artifact
itself, the implementation shown before the loop moves on, and the version put to the engineer
rather than decided by the agent.

**This file sits at the repository root for now.** Its final place is not settled, and the
content-areas aspiration records how an area becomes a page as still open.

---

**You:** add retries to the upload

**Agent:** The work runs through five hinges. A hinge is a decision the design turns on, and the loop stops at each one for you.

1. **Actuation** — the invocation of the unit, written as a use site would write it.
2. **Observation** — what the test reads about the effect the actuation produces.
3. **Controls** — the known inputs the test is built from.
4. **Implementation** — the code that satisfies the test.
5. **Naming** — the name of the outcome the test establishes.

The first three build the test. The fourth writes the code. The fifth is settled at the close. Everything between the hinges I generate without stopping.

`Upload#call` posts the file once. The first hinge:

```
╭─ Actuation ──────────────────────────────────────────────────────────────────╮
│                                                                              │
│  Two actuations differ in what the use site states.                          │
│                                                                              │
│  ❯ 1  upload.(file)                                                          │
│       The retry policy is the object's. No use site states it, and the       │
│       existing use sites do not change.                                      │
│                                                                              │
│    2  upload.(file, retries: 3)                                              │
│       The retry count is stated at every use site. The existing use sites    │
│       gain a keyword or take a default.                                      │
│                                                                              │
│    3  Explain                                                                │
│       Say what each shape commits the interface to, then display this        │
│       selection prompt again.                                                │
│                                                                              │
│    4  Other                                                                  │
│                                                                              │
│  ↑↓ select · ⏎ confirm                                                       │
╰──────────────────────────────────────────────────────────────────────────────╯
```
```
waytide · feature/upload-retries · uncommitted changes :: Waytide
```

**You:** `upload.(file)`

**Agent:** The actuation is `upload.(file)`.

```
╭─ Observation ────────────────────────────────────────────────────────────────╮
│                                                                              │
│  The observation reads the side effect from upload.(file).                   │
│                                                                              │
│  ❯ 1  assert(retries == 3)                                                   │
│       The count the upload returns, compared against the count it carries.   │
│                                                                              │
│    2  Explain                                                                │
│       Say what this observation witnesses, then display this selection       │
│       prompt again.                                                          │
│                                                                              │
│    3  Other                                                                  │
│                                                                              │
│  ↑↓ select · ⏎ confirm                                                       │
╰──────────────────────────────────────────────────────────────────────────────╯
```
```
waytide · feature/upload-retries · uncommitted changes :: Waytide
```

**You:** `assert(retries == 3)`

**Agent:** The controls hinge follows. The retry count is the object's, so the test arranges it here.

```
╭─ Controls ───────────────────────────────────────────────────────────────────╮
│                                                                              │
│  The client refuses. The count is stated here or left to the default.        │
│                                                                              │
│  ❯ 1  Controls::Upload.example(client: control_client, retries: 3)           │
│       The test states the policy it examines.                                │
│                                                                              │
│    2  Controls::Upload.example(client: control_client)                       │
│       The test rests on the upload's own default count.                      │
│                                                                              │
│    3  Explain                                                                │
│       Say what each control makes discriminating, then display this          │
│       selection prompt again.                                                │
│                                                                              │
│    4  Other                                                                  │
│                                                                              │
│  ↑↓ select · ⏎ confirm                                                       │
╰──────────────────────────────────────────────────────────────────────────────╯
```
```
waytide · feature/upload-retries · uncommitted changes :: Waytide
```

**You:** `Controls::Upload.example(client: control_client, retries: 3)`

**Agent:** The turn-one test file is assembled.

```ruby
context "Upload" do
  context "Call" do
    context "Retries" do
      control_client = Controls::HTTP::Client::Refusing.example
      control_file = Controls::File.example

      upload = Controls::Upload.example(client: control_client, retries: 3)

      retries = upload.(control_file)

      comment "Retries: #{retries.inspect}"

      test do
        assert(retries == 3)
      end
    end
  end
end
```

```
╭─ Implementation ─────────────────────────────────────────────────────────────╮
│                                                                              │
│  Two ways arrive at the same implementation.                                 │
│                                                                              │
│  ❯ 1  The working implementation, written directly                           │
│       The code that satisfies the test, with no deliberate failure first.    │
│                                                                              │
│    2  The red, green, refactor cycle                                         │
│       A failing implementation first. The red reaches no stable test.        │
│                                                                              │
│    3  Explain                                                                │
│       Say what the cycle buys here, then display this selection prompt       │
│       again.                                                                 │
│                                                                              │
│    4  Other                                                                  │
│                                                                              │
│  ↑↓ select · ⏎ confirm                                                       │
╰──────────────────────────────────────────────────────────────────────────────╯
```
```
waytide · feature/upload-retries · uncommitted changes :: Waytide
```

**You:** the working implementation, written directly

**Agent:** The implementation is written.

```ruby
class Upload
  attr_reader :client
  attr_reader :retries

  def initialize(client, retries)
    @client = client
    @retries = retries
  end

  def call(file)
    attempts = 0

    retries.times do
      attempts += 1

      response = client.post(file)

      break if response.accepted?
    end

    attempts
  end
end
```

The suite is run.

```
Upload
  Call
    Retries
      Retries: 3
      •

47 tests, 0 failed, 0 aborted
```

The outcome is verified. The refusal is retried to the count the object carries.

```
╭─ Naming ─────────────────────────────────────────────────────────────────────╮
│                                                                              │
│  Two names state what the observation establishes.                           │
│                                                                              │
│  ❯ 1  "Is the retry count"                                                   │
│       The assertion is a value comparison.                                   │
│                                                                              │
│    2  "Attempts reach the retry count"                                       │
│       Names the behavior rather than the comparison.                         │
│                                                                              │
│    3  Explain                                                                │
│       Say what each name promises a reader, then display this selection      │
│       prompt again.                                                          │
│                                                                              │
│    4  Other                                                                  │
│                                                                              │
│  ↑↓ select · ⏎ confirm                                                       │
╰──────────────────────────────────────────────────────────────────────────────╯
```
```
waytide · feature/upload-retries · uncommitted changes :: Waytide
```

**You:** `"Is the retry count"`

**Agent:** The test is named and the suite is verified.

**You:** release it

**Agent:** The gemspec records `1.4.1`.

```
╭─ Version ────────────────────────────────────────────────────────────────────╮
│                                                                              │
│  The next version is a claim about the code of everyone who installs this.   │
│                                                                              │
│  ❯ 1  1.4.2  Patch                                                           │
│       Behavior is corrected. The interface does not change.                  │
│                                                                              │
│    2  1.5.0  Minor                                                           │
│       A capability is added. Existing use is not affected.                   │
│                                                                              │
│    3  2.0.0  Major                                                           │
│       Existing use can stop working.                                         │
│                                                                              │
│    4  Explain                                                                │
│       Say what each claim commits you to, then display this selection        │
│       prompt again.                                                          │
│                                                                              │
│  ↑↓ select · ⏎ confirm                                                       │
╰──────────────────────────────────────────────────────────────────────────────╯
```
```
waytide · feature/upload-retries · uncommitted changes :: Waytide
```

**You:** `1.5.0  Minor`

**Agent:** The gemspec's `s.version` records `1.5.0`. Three commits are made.

1. `Upload retries` — the test and the implementation.
2. `Package version is increased from 1.4.1 to 1.5.0` — the gemspec.
3. The loop record, carrying the five hinges and the decision at each.

The gem is built with `gem build upload.gemspec` and published with `gem push upload-1.5.0.gem`. A published version does not come back.

---

Authored by Scott Bellware on Mon Aug 10 2026 at 12:08:15 PM PT
Changed by Scott Bellware on Mon Aug 10 2026 at 1:18:41 PM PT
