# FAQ

## Why is there no code?

On purpose. The agent writes parsers for the exports you have. The software can write itself.

## Which agent does it need?

Built with Claude Code. Other agents that run scripts and sub-agents should work. Untested.

## What can't the data do?

- See your childhood. The book says the Why forms by the late teens. Those stories come from memory.
- Weigh years fairly. Recent years dominate.
- Show deeds or feelings. Most of it is traces. A search shows interest, nothing more.
- Hear the people on the receiving end. The "so that" comes from you, and from your friends.
- Find your Why. It guesses. You decide.

*Find Your Why* is expert practice. No study shows that it, or any purpose exercise, improves decisions. Treat the result as a draft to live with.

## What does it cost?

**Time.** Half an hour to request exports, then a wait. A few hours of checkpoints. Interviews of 30 to 45 minutes. Themes: 2 to 3 hours over two sittings. Friends: 3 to 5, 20 to 30 minutes each.

**Tokens.** Depends how much you feed in. Start with two or three sources and let the agent run a pilot. The pilot is your estimate.

**Models.** Reading and verifying are most of the work. A mid-tier or small model handles them fine. Save the strongest model for judgement: the skeptic, the sealed thesis, the comparison and the interviews ([PROMPT.md](PROMPT.md), Model choice). My own run used one top model throughout, the expensive way.

## What did one full run look like?

A labelled example, not a benchmark:

> From 340,946 timestamped records (22 sources, 2011 to 2026), 173 Claude agents in 8 analysis runs worked through 66 text slices. All 6,605 evidence quotes were found in their source (91% at an unambiguous locator), yet verifier agents changed or dropped 39% of the extracted items (95% CI 37 to 42%, clustered by slice). $533 at API list price.
>
> A change is not an error. Nobody has yet checked by hand how many changes fixed a real mistake. List price means one model, no discounts. It ran on a subscription, so nothing was billed per token.

## Why seal in two stages?

My own run hashed both stages at once, in a private repo. That proves little. This kit writes the data thesis first and seals it before your first story. Your themes are sealed second. [COMPARE.md](COMPARE.md) has the steps.

## What's in the kit?

- [SOURCES.md](SOURCES.md): where to request each export.
- [PROMPT.md](PROMPT.md): the master prompt, with the privacy table.
- [READING.md](READING.md): briefs for the reader, verifier and skeptic agents.
- [INTERVIEW.md](INTERVIEW.md) and [THEMES.md](THEMES.md): the partner briefs. They run in fresh sessions, blind to the data's reading.
- [COMPARE.md](COMPARE.md): the seal and the comparison.

## What if it gets heavy?

Stop whenever you want. If a valley story opens something heavy, talk to a person you trust, not only to an AI.
