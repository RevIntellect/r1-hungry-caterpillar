# HANDOFF

Ultra overnight handoff. Next session starts here. Do not invent scope.

## Snapshot

| Field | Value |
| --- | --- |
| Date | 2026-09-17 |
| Repo | [RevIntellect/r1-hungry-caterpillar](https://github.com/RevIntellect/r1-hungry-caterpillar) |
| Base | `main` |
| Branch | `cursor/pages-handoff-62b6` |
| PR | https://github.com/RevIntellect/r1-hungry-caterpillar/pull/1 — **do not merge** |
| Owner tonight | None. Aaron does not need to enable Pages or merge. |
| Secrets | None. Do not add any. |

## Mission

Make this existing public HTML game a clean, deployable portfolio micro-demo: fix Pages-relative paths if broken, refresh README, add agent/handoff docs, add an in-repo Pages workflow that deploys from `main` after merge, open a PR.

## What it is

Snake-style caterpillar on a 240×282 Rabbit R1 canvas. Food tiles are lettered bites (`A` `P` `G` `C` `B` `N` `D`). Inputs: tap, keyboard, R1 `scrollUp` / `scrollDown` / `sideClick`. Everything lives in `index.html`.

## Done this session

- Inspected the repo: only `README.md` + `index.html`; no workflows; Pages was not enabled.
- Confirmed there were **no external asset URLs**. Game JS/CSS is inline. Project Pages (`/r1-hungry-caterpillar/`) does not break loads.
- Wrapped the board in `#app` (relative, 240×282) and centered that frame on a full-page body so the start/game-over overlay stays on the board on desktop Pages. R1 size unchanged.
- Added `.nojekyll` so Pages serves files as-is.
- Added `.github/workflows/pages.yml` (official static Pages actions: checkout → configure-pages → upload → deploy-pages). Triggers: push to `main`, `workflow_dispatch`. No secrets.
- Replaced the one-line README with purpose, local run, Pages URL, controls, layout, out-of-scope.
- Added `AGENTS.md`, `CLAUDE.md`, this `HANDOFF.md`.
- Opened a PR. Did not merge.

## How to run

```bash
python3 -m http.server 8000
# http://localhost:8000/
```

Or open `index.html` via `file://`.

## Pages (after merge to main)

- Expected URL: **https://revintellect.github.io/r1-hungry-caterpillar/**
- Workflow publishes the repo root. First green run on `main` creates the site.
- If that run fails because Pages source is still unset: **Settings → Pages → Source: GitHub Actions**. One click, no secrets, not required tonight.

## File map

| Path | Role |
| --- | --- |
| `index.html` | Game |
| `.nojekyll` | Disable Jekyll on Pages |
| `.github/workflows/pages.yml` | Deploy from `main` |
| `README.md` | Humans |
| `AGENTS.md` | Agents |
| `CLAUDE.md` | Short BLAST brief |
| `HANDOFF.md` | This file |

## Constraints honored

- No new product scope (no second screen, no score API, no bundler).
- No secrets.
- No Applause content.
- PR left unmerged.

## Explicitly out of scope

- Gameplay redesign, sound, sprites, high-score persistence.
- Custom domain / CNAME.
- Enabling Pages in the GitHub UI tonight.
- Merging this PR.
- Anything Applause / outbound-engine.

## Verification

Done locally on 2026-09-17 against `python3 -m http.server 8000`:

- `index.html` has no `src="/…"` or `href="/…"` asset paths.
- `/` and `/index.html` both serve the same game.
- Start overlay on-board → Enter starts → arrows steer → ate food (score 0→2) → wall death shows “full tummy” on-board → Enter restarts.
- Frame stays centered on a wide desktop window.
- Browser requested `/favicon.ico` (default; none shipped). Harmless 404, not a game asset. Do not add a favicon unless asked.

## Next human (after sleep)

1. Review the PR. Merge when ready.
2. Confirm Actions → **Deploy GitHub Pages** is green on `main`.
3. Open https://revintellect.github.io/r1-hungry-caterpillar/ and play once.
4. Optional: set the repo **About → Website** to that URL.

## Known leftovers (pre-existing, not this PR)

- `speed` decreases when food is eaten, but the loop stays `setInterval(loop, 200)`. Faster play was never wired. Do not “fix” unless asked.
