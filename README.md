# Why from your data

A prompt kit for finding your Why, with your own data as a memory aid. No software.

You download your data: notes, mail, chats, posts, search history. A coding agent builds a dated timeline from it. An AI partner interviews you about the moments that mattered, with the method from Simon Sinek's *Find Your Why*. Your stories pick your Why. The data may only add to it, challenge it or date it. A felt truth beats a trace.

There is no code here on purpose. The agent writes parsers for the exports you have. The software can write itself.

It is not a Why generator. It is not therapy.

---

## What you get

- **A timeline of the years your data covers.** Eras, events, and where the data is blind.
- **20 to 25 story prompts.** Dated peaks and valleys, each with a line you wrote back then.
- **Interviews with an AI partner** told to ask, listen and write down your words, never to interpret. Watch that it doesn't.
- **A themes session.** From stories to "To ___ so that ___", and your Hows.
- **Optional: a sealed comparison.** Agents guess your Why from the data, sealed before your first story. You open it after your own themes are sealed.

## What the data can't do

- See your childhood. The book says the Why forms by the late teens. Those stories come from memory.
- Weigh years fairly. Recent years dominate.
- Show deeds or feelings. Most of it is traces. A search shows interest, nothing more.
- Hear the people on the receiving end. The "so that" comes from you, and from your friends.
- Find your Why. It guesses. You decide.

*Find Your Why* is expert practice. No study shows that it, or any purpose exercise, improves decisions. Treat the result as a draft to live with.

## What it costs

**Time.** Half an hour to request exports, then a wait. A few hours of checkpoints. Interviews of 30 to 45 minutes. Themes: 2 to 3 hours over two sittings. Friends: 3 to 5, 20 to 30 minutes each (this kit's suggestion).

**Tokens.** It depends on how much you feed in. Start with two or three sources. The agent runs a pilot. The pilot is your estimate.

**One person's run.** A labelled example, not a benchmark:

> From 340,946 timestamped records (22 sources, 2011 to 2026), 173 Claude agents in 8 analysis runs worked through 66 text slices. All 6,605 evidence quotes were found in their source (91% at an unambiguous locator), yet verifier agents changed or dropped 39% of the extracted items (95% CI 37 to 42%, clustered by slice). $533 at API list price.
>
> A change is not an error. Nobody has yet checked by hand how many changes fixed a real mistake. List price means one model, no discounts. It ran on a subscription, so nothing was billed per token.

---

## What leaves your machine

Parsing and storage stay local. But the coding agent is a cloud model. What it reads goes to the provider. A local model can do the reading runs, through a runner the agent writes. It is weaker, and untested here. The interviews go to the cloud either way.

| Phase | What reaches the model provider |
|---|---|
| 0 to 2: consent, inventory, parsers | your answers; folder names and counts; export structure; sample rows only after a yes |
| 3: slices | nothing |
| 4 to 6: reading, timeline, thesis | every slice read; `profile.md`; any file an agent opens. Nothing with a local model. |
| 7, 8: interviews, themes | everything you say; your stories |
| 9: compare | slices, extractions, thesis, stories, themes |

The seal posts one hash per stage. It reveals nothing.

**Defaults.** Own lines only from chats and mail, with quoted replies stripped. Search history stays local. Money off. Pseudonyms for people. You can change each one, per source.

**Know this.** A pseudonym doesn't anonymise. The people in your data never agreed to this. Exclusion filters miss things: spot-check them. A deny rule is a guard. Moving or encrypting files is the lock. Your provider's data terms apply.

**Before you share:** aggregates only. Scan each file against a local list of the names and places in your data. Never push the working folder.

---

## How to start

1. Request your exports now. [PROMPT.md](PROMPT.md), phase 1, lists the useful ones.
2. In a new folder, put the exports in `exports/` and this kit in `kit/`: the ZIP, or a clone with `kit/.git` deleted.
3. Open Claude Code there. Say: "Read kit/PROMPT.md and follow it."
4. The agent stops at every checkpoint.

Built with Claude Code. Other agents that run scripts and sub-agents should work. Untested.

**Files.** [PROMPT.md](PROMPT.md), the master prompt. [READING.md](READING.md), for the reader, verifier and skeptic agents. [INTERVIEW.md](INTERVIEW.md) and [THEMES.md](THEMES.md), the partner briefs, run in fresh sessions blind to the data's reading. [COMPARE.md](COMPARE.md), the seal and the comparison.

---

## What worked, what didn't

I ran a lean version of this once, on my own data.

**What worked: the timeline and the interviews.** They brought back so many memories, and a true timeline.

**What didn't: the Why.** It mostly held up against the data. But it felt weak. It didn't mean much. I'm not really behind it.

**The likely cause: the lean path.** Five stories, the book's minimum. One 45-minute themes sitting.

**The comparison** showed the data was good at what I do. It was weak at how it felt and what it did for others. And agreement came cheap: my stories came from the data's own prompts.

**Next time.** Seven to ten stories. Two themes sittings. The Friends Exercise in between. No decisions on a Why until I'm behind it.

**My seal was weak.** It hashed the thesis and my themes at the same moment, in a private repo. That shows me neither changed after. It shows nobody else anything: a private commit's time can be rewritten, and no one can re-hash a file they never see. Nor does it show which came first. And the thesis was written while I told stories. Its agents could see the titles of the stories told, not what I said. This kit seals in two stages and writes the thesis first.

---

## A note of care

This can stir up hard things. Stop whenever you want. If a valley story opens something heavy, talk to a person you trust, not only to an AI.

## Credits

The method: Simon Sinek, with David Mead and Peter Docker, *Find Your Why: A Practical Guide for Discovering Purpose for You and Your Team* (Portfolio, 2017). The Friends Exercise: Simon Sinek Inc., [free PDF](https://simonsinek.com/uploads/books/find-your-why/find-your-why-friends-exercise.pdf).

This kit paraphrases the method. Read the book. The kit is not affiliated with or endorsed by the authors. The data pipeline, the seal and the comparison rules are its own.

Licence, suggested: [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).
