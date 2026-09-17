# AGENTS.md

## What this repo is

Public static HTML game for Rabbit R1, also used as a portfolio micro-demo. One playable file: `index.html`.

## Before you change anything

1. Read `HANDOFF.md` and this file.
2. Do not invent scope. Do not pull Applause content. Do not add secrets.
3. Keep the playfield **240×282**. Overlay (`#go`) must stay inside `#app` (`position: relative`) so it still sits on the board when the page is a full desktop viewport.

## How to run

```bash
python3 -m http.server 8000
```

Open http://localhost:8000/ — or open `index.html` directly.

## Pages

- Workflow: `.github/workflows/pages.yml`
- Deploys **from `main` after merge** (plus `workflow_dispatch`)
- Expected URL: https://revintellect.github.io/r1-hungry-caterpillar/
- If a first deploy errors on Pages source, set **Settings → Pages → Source: GitHub Actions**
- Add `.nojekyll` stays at repo root so Jekyll does not rewrite the site

## Path rules (GitHub Pages)

This is a **project** Pages site, not a user root site. Assets must be relative (`./file`, `assets/x.png`), never `/file` or `https://localhost`. Today there are no external assets. If you add any, keep them next to `index.html` or under a relative folder and update the Pages note in `README.md`.

## Do / don't

- **Do** keep the game playable with tap and keyboard (R1 events are extra, not the only input).
- **Do** leave PRs unmerged unless the owner asks.
- **Don't** add npm, frameworks, tracking, env files, or a second game.
- **Don't** change food letters/colors unless asked — they are the existing art.

## Verify

Serve locally, load `/`, confirm start overlay, start with click or Enter, steer, eat, die, restart. Confirm the HTML has no root-absolute `src`/`href`.
