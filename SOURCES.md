# Sources

Where to get your data. Official pages only, checked 18 Oct 2026.

Request these now. They take no time to request, only time to wait. [PROMPT.md](PROMPT.md), phase 1, is the checkpoint where you pick which ones to parse first.

| Source | Link | Format | Wait | What it gives |
|---|---|---|---|---|
| Google Takeout | [takeout.google.com](https://takeout.google.com) | JSON where offered; Calendar is always `.ics` | Minutes to a few days | Tick My Activity (Search, YouTube), Keep, Maps, Calendar. Gmail is optional, and large. |
| Google Maps Timeline | On your phone: Android, Settings > Location > Timeline > Export Timeline data. iPhone, Maps app > profile > Settings > Location & Privacy > Export Timeline data. [Google's guide](https://support.google.com/maps/answer/6258979) | JSON, saved to the phone | Instant | Visited places and routes. Moved on-device in 2024. Not in Takeout any more. |
| Meta Accounts Center | [Download your information](https://help.instagram.com/181231772500920) | JSON, date range "All time" | Minutes to a day | Facebook and Instagram together: posts, messages, search history. |
| X | [Download an archive of your data](https://help.x.com/en/managing-your-account/how-to-download-your-x-archive) | ZIP, mostly JSON | Up to 24 hours | Every post, like, reply, and bookmark. |
| LinkedIn | [Download your data](https://www.linkedin.com/help/linkedin/answer/a1339364/downloading-your-account-data) | ZIP of CSV files, no JSON option | Up to 24 hours, pick the full archive, not a category | Messages, posts, connections, search history. |
| Amazon | [Request your data](https://www.amazon.com/gp/help/customer/display.html?nodeId=TP1zlemejtTn6pwYKS) | JSON | 1 to 3 days | Orders and Kindle reading insights. Highlights come off the device, see below. |
| Kindle library | Plug it in by USB, copy `documents/My Clippings.txt` | Plain text | Instant | Every highlight and note, with the book title attached. |
| Spotify, account data | [Account privacy](https://www.spotify.com/account/privacy/) | ZIP of JSON | A few days | About the last year of streams, playlists, your taste profile. |
| Spotify, extended history | Same page, tick "Extended streaming history" too | ZIP of JSON | Up to a month | Every track played since you joined, timestamped. |
| Claude | Settings > Privacy > Export data. [How it works](https://privacy.claude.com/en/articles/9450526-export-your-claude-data) | ZIP of JSON | Usually minutes; link expires in 24 hours | Every conversation plus account data. Web and desktop only, not mobile. |
| ChatGPT | Settings > Data controls > Export. [How it works](https://help.openai.com/en/articles/7260999-exporting-your-chatgpt-history-and-data) | ZIP of JSON | Up to 7 days | Every conversation plus account data. |
| GitHub | Settings > Account > Start export. [How it works](https://docs.github.com/en/get-started/archiving-your-github-personal-account-and-public-repositories/requesting-an-archive-of-your-personal-accounts-data) | `tar.gz` | Usually fast; link expires in 7 days | Issues, comments, and the commit metadata tied to your account, not the code itself. |
| Apple, optional | [privacy.apple.com](https://privacy.apple.com) | Varies by data type | A few days | iCloud notes, mail, calendar, purchase history. |
| Notion, if you keep notes there | [Export your content](https://www.notion.com/help/export-your-content) | Markdown and CSV | Minutes, up to 30 hours for a big workspace | Every page as its own file, in your own folder structure. |
| Obsidian, if you keep notes there | No export. Point the agent at the vault folder. | Markdown | None | Already on disk. |

No `gh` command does a personal data export today. Use the GitHub settings page above.

## A good first set

Start with three to five. These give the most story per hour of waiting and reading.

- **Your notes and journal.** Already yours. No wait, no request.
- **Sent mail.** From Google Takeout. The side you wrote.
- **Google My Activity: Search and YouTube.** What you looked up and watched, and when.
- **Your own chat messages.** Own side only, per the kit's default. Strip the other person's lines before anything gets read.
- **A reading list.** Kindle highlights, or a Goodreads export if you keep one there.

## Skip at first

- **Photos.** The dates help the timeline. The images themselves don't.
- **A full Drive copy.** Mostly other people's files and old spreadsheets.
- **Bank data.** The kit turns money off by default. Add it later, if at all.

## A note on these links

Services move their settings around. If a link above is dead, search the service's help center for "download your data" or "export your data." The steps rarely change; the menu path does.
