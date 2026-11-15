# AIP-PAGE

The website of AI-Project (AIP), HS 2026: https://eth-aip-hs26.github.io/AIP-PAGE/

| Path | What | Who sees it |
|------|------|-------------|
| `hub/` → `/` | the public hub: the four projects (previews coming soon; later one page per weekend and project) | everyone |
| `team/` → `/team/` | the TA team's meeting place, built with [meeting-engine](https://github.com/ElisejOrsini/meeting-engine/blob/v0.9.3/docs/private-course.md) | signed-in team members only |

This repository is public. It holds the public hub and the meeting place's
settings (`team/course.yml`), **never meeting content**: meetings, the team
list and survey answers live in the database. Don't add notes, transcripts or
anything internal here.

## Rule for the public hub

The hub and the team's meeting place share one web address, and the meeting
place keeps the team's sign-in in the browser for that address. So the hub
must **never load anything from other websites**: no analytics, trackers,
fonts or scripts from a CDN, and no embeds. A script from elsewhere could read
the team's sign-in. Libraries are fine when they are copied into this
repository and served from here. Keep the page's Content-Security-Policy
(in `hub/index.html`) strict.

## Deploying

Every push to `main` publishes the site (`.github/workflows/deploy.yml`).
Updating the meeting place: change the engine version (`@v0.9.3`) there.
