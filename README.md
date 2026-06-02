# Swarm Online Workshops

> **Maintained by:** devrel team

Landing page for the **Swarm Online Workshops** — a series of free, hands-on live
sessions to learn, build, and use [Swarm](https://www.ethswarm.org), the
decentralized storage and communication network.

The site lists past workshops as a rewatchable archive (YouTube recordings) and
provides calendar invites, links to recordings, and pointers to the wider Swarm
ecosystem. It is published at **https://workshops.swarm.bzz.link/** and served
over Swarm itself (the `.bzz.link` gateway).

## Tech stack

A deliberately simple, dependency-free static site:

- **`index.html`** — the single landing page (hero + workshop cards + footer).
- **`styles.css`** — all styling. No framework, no build step.
- **`assets/`** — thumbnails, logos, the Open Graph image, and the workshop PDF.
- **`calendar/`** — downloadable `.ics` calendar invites, one per workshop.

There is no build tooling, package manager, or server-side code. Everything is
plain HTML/CSS that can be opened directly in a browser.

[Matomo](https://mtm.swarm.foundation/) analytics (self-hosted, site ID `20`) is
loaded inline in `index.html` for privacy-respecting page tracking.

## Project structure

```
.
├── index.html      # Main landing page
├── styles.css      # All styles
├── assets/         # Images, logos, OG image, workshop PDF
│   ├── general.png
│   ├── Horizontal_Orange.png        # Swarm wordmark logo
│   ├── Mark_Orange.png              # Swarm mark (favicon)
│   ├── Intro-to-swarm.png           # Workshop thumbnails ↓
│   ├── workshop1.png
│   ├── workshop2.png
│   ├── workshop3.png
│   ├── workshop-og.png             # Open Graph / social share image
│   └── Swarm MCP - AI Workshop.pdf # Presentation slides
└── calendar/       # .ics calendar invites
    ├── swarm-intro-to-swarm-march-2026.ics
    ├── swarm-workshop-2-ai-agent-april-2026.ics
    ├── swarm-workshop-2-frontend-may-2026.ics
    └── swarm-workshop-3-streaming-may-2026.ics
```

## Workshops

All sessions stream live on **YouTube** (primary) and **X** (secondary), and
remain available as recordings afterwards. Times are displayed in **CET**.

| Date | Workshop | Recording |
|------|----------|-----------|
| Mar 25, 2026 | Intro to Swarm | [YouTube](https://youtube.com/live/lkrNZJFCmOc) |
| Apr 8, 2026 | Workshop 1 — AI Agent | [YouTube](https://youtube.com/live/AP6Wr8f2m2Q) |
| May 5, 2026 | Workshop 2 — Frontends | [YouTube](https://youtube.com/live/ofsKcDHRgv0) |
| May 12, 2026 | Workshop 3 — Streaming | [YouTube](https://youtube.com/live/1vJnUOSp1ug) |

The page currently shows only **past workshops** as a rewatchable list. When new
sessions are scheduled, the layout can be restored to its three-section pattern
(upcoming banner + "Coming Next" grid + "Past Workshops" grid).

## Local development

No tooling required. Either open the file directly:

```sh
open index.html
```

…or serve the folder over a local HTTP server (recommended, so relative asset
and calendar paths resolve correctly):

```sh
python3 -m http.server 8000
# then visit http://localhost:8000
```

Edit `index.html` and `styles.css` and refresh the browser — there is no
compilation or hot-reload step.

## Deployment

The site is hosted on **Swarm** and reachable via the `bzz.link` gateway at
[workshops.swarm.bzz.link](https://workshops.swarm.bzz.link/). Because it is a
static bundle, deploying means uploading the directory contents to Swarm and
pointing the domain at the resulting reference.

## Related links

- **Swarm** — https://www.ethswarm.org
- **Docs** — https://docs.ethswarm.org
- **Swarm MCP** (used in the AI Agent workshop) — https://github.com/ethersphere/swarm-mcp
- **GitHub (Ethersphere)** — https://github.com/ethersphere
- **Discord** — https://discord.gg/dUS68y87U4
- **X / Twitter** — https://x.com/ethswarm
