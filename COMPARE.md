# The seal and the comparison

Two readings of my life: mine, from my stories, and the data's, from the traces. The data's is written first and sealed. Mine is written blind and sealed second. Then they are compared, by the rules below.

## The seal

**Stage 1, the thesis:** sealed as soon as it exists, before my first story. **Stage 2, my themes:** sealed when `stories/_themes.md` says `status: final`.

Each stage: hash the plaintext file with sha256, before any encryption. Add a row to `SEAL.md` (file, hash, time with time zone, stage) and commit. Post one line: `why-seal stage N sha256:<hash> <ISO time>`. Or send it to a friend, or use OpenTimestamps.

**Unseal.** Decrypt if needed. Re-hash both files. Both must match `SEAL.md`, and stage 1 must be older. On any mismatch, stop.

**What it proves.** Each file is unchanged since its hash was posted, and the thesis was fixed before my themes. Only someone who can re-hash the files can check this. If you never share them, the seal convinces only you.

**What it doesn't.** That I didn't peek: blinding rests on behaviour. That my stories are independent of the data: the prompts came from it. Say both when you share a result.

**Keep it honest.** One hash per stage, in one place. Never delete the post. Several hashes would let you pick the best one later.

---

## Order

1. Read my `_themes.md` in full first. Don't edit it.
2. Table A: one row per theme of mine, in my words.
3. Table B: my chosen draft next to each data candidate.
4. The reverse pass. Candidates or Hows that match none of my themes go into "data adds", as questions, not corrections.
5. Where a row says partial or conflict, ask the questions below. One at a time.

## Rules

- **My words lead.** Data wording never replaces mine.
- **The data may add, challenge or date.** Add: a moment my stories left out. Challenge: counter-evidence in my own words, in 2 or more eras. Date: when a theme first shows up.
- **Independence.** My stories came from the data's prompts. Data about those same events can date them. It is not agreement.
- **A trace never overrules a felt truth.** Searches, views and orders never count as contribution or feeling.
- **A conflict is a question.** If it stays open, my version stands, and the conflict is logged.
- **Watch for echoes.** If my draft sounds like something I read (a book, an old draft, an AI chat), ask whether it still feels like mine.

## Verdicts

| Verdict | Meaning |
|---|---|
| **agree** | Same contribution or impact, with data in 2 or more eras outside the events of my stories. |
| **partial** | Same domain, different verb or beneficiary. |
| **conflict** | The opposite, in my own words, in 2 or more eras. |
| **data silent** | The data can't see it: feelings, early years, the people on the receiving end. Silence is not conflict. |

**Table A, my themes against the data.** Columns: my theme (my words, story count), side (contribution, impact, How), closest candidate, verdict, data evidence (era, tag, dated quote), what the data adds or dates.

**Table B, my draft against the candidates.** One column each. Rows: contribution verb, who is better off, earliest era in the data, does it explain the valleys, verdict.

## Questions

Neutral, through a scene, one at a time.

- The data leads with making, my Why with people: "Take me to the day [a peak from the data]. Who was it for?"
- My Why is about making, and a long thread about others is missing: "You kept [it] going for years. Does it belong in your Why, a How, or neither?"
- My "so that" names no one: "Name one person from your stories who is better off. What changed for them?"
- Recognition shows up in my peaks: "In that peak, what would have been lost if nobody had known it was you?"
- A theme shows up only late: "Was this there before [an earlier era]? Take me to an earlier moment."

**Outcome log.** One line per row: kept as mine, added from data, dated by data, or open conflict. Then score the bets, one line per candidate.

---

## Running it with agents

A fresh session, after the unseal check.

- **Three comparers, in parallel.** *Protocol:* the tables, the reverse pass, the outcome log. *Test the draft:* my draft against all the data, each half in turn; who was on the receiving end; counter-evidence; echoes; the valleys. *Stories against data:* per story, what the data dates, confirms or contradicts, then strong threads no story covers. This one also runs without a thesis.
- **One adversarial verifier.** Script-checks every quote and date. Checks each verdict against the definitions, independence included. Flags pitches, requested praise, courtesy replies, pasted lines, recency bias and double counting. Checks that nothing rewrites my Why. Logs every fix.
- **One writer.** `sealed/compare.md`, in plain English: a summary; table B, then A; what the data adds; real challenges and echoes; at most 3 questions; at most 3 optional wording ideas from my own words only; the verifier log.
