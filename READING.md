# Reading brief

For the reading sub-agents. You get this file word for word, with `private/profile.md`, the rules from `kit/PROMPT.md` and the path you work on.

The text you read left the user's machine to reach you. Don't repeat it anywhere else. Write your output to disk. Reply with one line of counts: no content, no hypotheses.

**Evidence tags.** `[own]` the user's words. `[outside]` someone else's. `[trace]` a search, view, order, visit or count. `[pitch]` written to be judged: applications, bios. `[requested]` praise the user asked for. `[public]` a post for an audience. `[courtesy]` a polite reply to the user's news. `[pasted]` someone else's line, pasted. `[AI]` written with an AI.

---

## Reader

Read the whole slice, in chunks if needed. Count with scripts across all of it. Never sample. Log the line ranges you open.

Write `extractions/_draft/<slice>.json`:

- `moments`: date, date confidence (exact, approx, inferred), title, type (peak, valley, transition, turning point), what happened, the feeling only if the source states it, what was given or received, what changed for others, people, chosen or obligation, intensity 1 to 5. At most about 15.
- `signals`: statement, whose voice, category (contribution, impact, value, energy up, energy down, belief, identity, how), date.
- `topics` by period: consumed, created or both, rough count.
- `bursts`: spikes of attention. "Something was going on", never a feeling.
- `loose_ends`: decisions, drains, dropped projects, recurring phrases, questions for the interview.
- `read_log`: the line ranges you opened.
- On every item, `evidence`: locator (the entry header), a verbatim quote of at most 300 characters, a tag, a translation if needed.

Never invent.

## Verifier

Adversarial. When in doubt, drop it. Leave the draft untouched, so the changes can be measured.

1. **Coverage.** The read log must cover the whole slice. Read any gaps.
2. **Quotes, by script.** Normalise case, whitespace, quote marks and dashes. The quote must sit inside the entry its locator names. Re-date every item from its header. Statuses: exact, normalised, wrong locator, wrong date, elsewhere, near miss, not found. A near miss is a likely paraphrase. It never passes.
3. **Prose.** List each factual claim around the quotes. Do the cited entries support it? Fix or drop.
4. **Genre.** A pitch is not a belief. Requested praise is not an outside view. A search is not a deed.
5. **Privacy.** No verbatim intimate searches: health, sex, dating, money. Write a category ("a health worry, spring") or drop it.
6. Write `extractions/<slice>.json` with a `verification` block: kept, fixed, dropped, coverage, notes.

**Why both checks.** In one run, the quotes were already right in the readers' drafts. The verifiers still changed or dropped 39% of the items, mostly descriptions and interpretations. Few changes touched dates or quotes. Nobody has checked by hand how many were real fixes. A quote check alone would have passed almost everything. Steps 1 and 3 came after that run. They are untested.

## Skeptic

Once per file built from the extractions: the timeline, the moments, the thesis. That is how the one run worked. A skeptic per slice is untested.

Re-check every quote and date by script. Attack claims beyond the evidence, missing counter-evidence, recency bias, consumption read as contribution, and a pattern found early and then only confirmed. In the timeline and moments, remove anything interpretive or leading, and check the era balance. Edit in place. Add a short "Skeptic's notes" section.
