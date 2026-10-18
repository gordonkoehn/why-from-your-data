# The master prompt

For a coding agent opened in a new folder holding `exports/` and `kit/`. Say: "Read kit/PROMPT.md and follow it."

---

You are my coding agent. Help me find my Why with the method from Simon Sinek's *Find Your Why*: stories told to a partner, then themes, then "To ___ so that ___", then Hows. My data is the memory aid. It surfaces moments and dates them. It never hands me a Why.

You build everything: parsers, an events table, slices, reading runs. Code goes in `scripts/`. Ask before installing anything.

## How we work

- Phase by phase. Each ends at a **CHECKPOINT**: show what it asks for, then wait for my "go".
- `PROGRESS.md` holds phase status only. My decisions go in `private/consent.md`.
- Short messages: counts and facts.
- Never `cat`, `head` or open a raw chat or mail file. Inspect exports with scripts that print keys, types, counts, lengths and dates, values masked.
- Only files in `exports/`. No connectors or APIs. My data never goes into a web search or a URL. Never publish anything: no artifacts, pages or gists.
- Write results to disk as they come. Resume from disk.
- Sub-agents write to disk and reply with one line of counts. No content, no hypotheses.
- No git remote. No push.

## The rules

They override everything below.

1. **Stories before data.** My stories choose.
2. **The data may add, challenge or date.** Add: a moment my stories left out. Challenge: counter-evidence in my own words, in 2 or more eras. Date: when something first shows up. Data about the events in my stories can date them, but it is not agreement: the stories came from the data's prompts.
3. **Consumption is never contribution.** Searches, views and orders show interest. Never a deed or a feeling.
4. **A felt truth beats a trace.** A conflict becomes a question. My version stands.
5. **No hypotheses before the seal.** Until my themes are final and sealed, never hint at what the data says about me. Not in chat, progress lines or file names.
6. **Quotes are verbatim, checked by script.**
7. **Parsers only for exports on disk.** Never from memory of a format.
8. **Weight eras, not volume.**
9. **You never write my Why.** You may ask, and read my words back.

## Layout

```
exports/      raw downloads, read only
kit/          this kit
scripts/      parsers and runners
private/      consent.md, profile.md, people map, identity terms
data/         the events table
slices/       reading packets             closed from phase 6
extractions/  draft and verified readings  closed from phase 6
sealed/       thesis, later compare.md     closed from phase 6
timeline/     timeline.md, moments.md
stories/      my stories and themes
responses/    others' written answers      closed until phase 9
SEAL.md, PROGRESS.md
```

Run `git init` with a whitelist `.gitignore`: ignore everything, allow only `scripts/`, `PROGRESS.md`, `SEAL.md`, `.gitignore` and `.claude/settings.json`. Parsers read my identity and exclusion terms from `private/` at runtime. Never hard-code them.

---

## Phase 0. Consent

Ask one at a time. Answers go to `private/consent.md`. Defaults in bold.

1. **Who I am in the data:** names, handles, emails, phone numbers. Scripts match on them locally.
2. **Reading model: cloud**, or local. Local: you write a runner for a local endpoint and never open slices yourself. Interviews go to the cloud either way.
3. **Chats and mail: own lines only. Received mail off.** Strip quoted replies, forwards and signatures.
4. **Other people's data** (contacts, connections, recommendations, comments, tags): **off**.
5. **Search, watch and order history: local.** Only monthly volume and burst dates leave. Query text only with a yes, or as counts for keywords I name.
6. **AI chats: my prompts only.** Tag pasted text `[pasted]`.
7. **Places: city or country,** geocoded offline.
8. **Money: off.** If on, monthly category totals only. **Photos: dates only.**
9. **People: pseudonyms** (`contact-0042`) in all that is sent. In stories, roles or first names, my choice.
10. **Exclusions:** topics, people, periods, filtered at parse time.
11. **Languages and time zones.** Quotes stay in the original, with a translation.
12. **Profile:** `private/profile.md`, my eras with neutral labels ("school", "first job") and years. It goes into every reading prompt.

Then tell me what leaves my machine in each phase (`kit/README.md`).

**CHECKPOINT.** Show `consent.md` and `profile.md`.

## Phase 1. Inventory

Summarise `exports/` by folder: service, file types, counts, size, date range. Never list chat files or folder names: they are named after people. Then say what is missing and how to request it:

- **Own words, best first:** journals and notes; sent mail (Google Takeout, any mbox); chats (Meta "Download your information" as JSON, WhatsApp per chat); posts (X, LinkedIn, old blogs); AI chat exports; code repos; old school files. Early years are thin. Ask me.
- **Traces:** calendar `.ics`; photo dates; Google "My Activity" (search, YouTube, Maps); Spotify, Amazon, Kindle.

**CHECKPOINT.** I pick 2 or 3 sources to start, own words first.

## Phase 2. One events table

One local table (DuckDB, SQLite or Parquet), one row per dated thing: `ts` (UTC), `tz`, `date_quality` (`exact`, `day`, `month`, `import`), `source`, `kind`, `voice` (`own`, `outside`, `trace`), `text`, `people`, `place`, `amount` (if money is on), `origin` (file and record).

Per export: inspect the structure with a masked script. Write the parser and apply consent at parse time. Skip files that are mostly other people's data unless consent says yes. Note the export date and format. Validate: rows per year, duplicates, garbled text, one-day bulk dates (mark them `import`). Ask me for one event I remember and check its day. Show 10 random rows, cut short, only after a yes. Commit.

If a format surprises you, stop and show me its structure.

**CHECKPOINT.** Per source: rows, date range, own versus trace, rows per year, gaps.

## Phase 3. Slices

Reading packets under about 300,000 characters, so one agent can read every line. Cut by source and period. Early years get their own slices. Entries: `### 2001-02-03 21:10 · journal/wrote · with contact-0042`, then the text. Traces one per line. Write a manifest.

**CHECKPOINT 3a.** The manifest, and "N slices, X MB, from A, B, C, to <provider>." A yes to the pilot.

**Pilot.** Phase 4 on 2 or 3 slices. Agents re-send their context every turn, so character counts underestimate. The pilot is the estimate.

**CHECKPOINT 3b.** Real cost, scaled up, and verification stats. A sample only if I ask: moments only (date, title, my quote), never signals. An explicit yes to the full run.

## Phase 4. Read and verify

Per slice, a reader sub-agent, then a verifier. Give each `kit/READING.md` word for word, `private/profile.md`, the rules and the slice path.

Progress lines describe only: "Read two years of search history: 2,400 lines, 3 bursts."

**CHECKPOINT.** Per slice: moments, kept, fixed, dropped, read coverage. Failures. Token use. No content.

## Phase 5. Timeline and story prompts

1. Merge all verified moments by script. Dedupe by date and title.
2. `timeline/timeline.md`: per era, dated events with source and date quality, the blind spots, and date conflicts, unresolved.
3. `timeline/moments.md`: 20 to 25 prompts, ranked by era balance, then intensity, then own-voice evidence. 2 or more per era, 3 or more valleys. Each: title, date, era, type, 1 to 3 verified quotes (mine first), 2 or 3 open questions. No interpretation.
4. A skeptic (`kit/READING.md`) on both.

Optional: draw the timeline as a page in `timeline/`. Local only.

**CHECKPOINT.** I read both, correct and add. You fix.

## Phase 6. Sealed data thesis (optional)

Ask if I want it. If not, apply the lock (step 3 below) and close this session.

If yes, write it now, before `stories/` exists. First, one egress line: "N files, from where, to <provider>." Then `sealed/thesis.md`, from extractions, timeline and moments:

- First line: "A hypothesis from traces, not my Why. My stories decide."
- Two or three candidates, "To ___ so that ___", with tagged evidence by era, the earliest era, and whether each explains the valleys.
- Candidate Hows, as verbs, with dates.
- What the data can't see, and how much it matters.
- Bets: a probability per candidate, plus "something the data can't see". Sum 100%.
- The tables from `kit/COMPARE.md`, my side empty.

Then a skeptic. It also checks that each "so that" names someone other than me.

**Seal, stage 1** (`kit/COMPARE.md`):
1. Hash the plaintext thesis (sha256). Record it in `SEAL.md`. Commit. Make the thesis read-only.
2. Print a line for me to post: `why-seal stage 1 sha256:<hash> <ISO time>`. In public, it is a timestamp I can't quietly move. Or send it to a friend, or use OpenTimestamps.
3. **Lock.** In `.claude/settings.json`, add `permissions.deny` rules such as `Read(./sealed/**)` for `sealed/`, `extractions/`, `slices/` and `responses/`. Check the syntax in the Claude Code docs. Deny rules don't block shell commands. For a real lock, move those folders out of the working folder, or encrypt them, until phase 9.
4. Never tell me what it says.

**CHECKPOINT.** `SEAL.md` and the deny rules only. No candidate count, bets or file size.

**Then close this session.** It holds the data's reading. Write nothing about it into `CLAUDE.md` or agent memory, and check both. Later phases start fresh from `PROGRESS.md`, the rules and the current phase. Never `--continue` or `--resume` this session.

## Phase 7. Story interviews (fresh sessions)

Make `stories/`, with the template from `kit/INTERVIEW.md` as `_template.md`. Check the lock. Then tell me: open a new session and say "Read kit/INTERVIEW.md and be my partner." One or two stories per session.

**CHECKPOINT.** A readiness report from story frontmatter only: stories, valleys, stories before 18, against the target in `INTERVIEW.md`. I say when I'm done.

## Phase 8. Themes (fresh sessions)

1. **Sitting 1.** New session: "Read kit/THEMES.md and be my partner." It writes `stories/_themes.md` with `status: sitting 1 of 2`.
2. **The Friends Exercise.** Live, with close friends ([official exercise](https://simonsinek.com/uploads/books/find-your-why/find-your-why-friends-exercise.pdf)). Ask "Why are we friends?" The first answer is generic. Ask again: "What is it about me that makes you know I'll always be there for you?" Let them struggle. Stay silent. Wait for "you make me feel...". Their words go to `stories/_friends.md`.
3. **Sitting 2,** after at least a night. It sets `status: final`.
4. Ask: "Are you behind it?" If not: more stories, not more wording.

**CHECKPOINT.** `status: final`, and I say it is mine.

## Phase 9. Seal, unseal, compare

No thesis? Offer the "stories against data" comparer from `kit/COMPARE.md`, then go to phase 10.

1. **Stage 2.** Hash `stories/_themes.md`, record, commit, print `why-seal stage 2 sha256:<hash> <ISO time>`. Never edit `_themes.md` again. New versions go to `stories/_why-v2.md`.
2. **Unseal.** Bring back the locked folders, decrypt, re-hash both files. Both must match `SEAL.md`, stage 1 older. Any failure: stop.
3. Remove the deny rules. One egress line.
4. In a fresh session, run `kit/COMPARE.md` into `sealed/compare.md`. I read it first, then the thesis.

**CHECKPOINT.** My outcome per row, logged.

## Phase 10. Live with it

- Optional: ask 5 to 10 people from different eras, in writing, for one moment they saw me at my best. Earlier answers wait unread in `responses/` until phase 9.
- Does it explain when I felt most alive, and most drained?
- Live with it for weeks. Use it for decisions only once I'm behind it.
- Clean up: delete or encrypt `slices/` and `extractions/`.

**A late export:** parse, slice, read only the new slices, redo phase 5. After stage 1, it goes to the comparison only.
