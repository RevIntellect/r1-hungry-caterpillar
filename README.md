# Hungry Caterpillar

A self-contained [Rabbit R1](https://www.rabbit.tech/) micro-game: steer a caterpillar, eat labeled bites, grow. One HTML file, no build, no backend, no secrets.

This repo is a public portfolio micro-demo. Play it locally or, after this branch merges to `main`, on GitHub Pages.

## Play locally

Clone and open the game. There are no dependencies.

```bash
git clone https://github.com/RevIntellect/r1-hungry-caterpillar.git
cd r1-hungry-caterpillar
```

Either:

- Open `index.html` in a browser (works over `file://`; nothing is fetched), or
- Serve the folder:

```bash
python3 -m http.server 8000
```

Then open [http://localhost:8000/](http://localhost:8000/).

## GitHub Pages (after merge)

Live URL once Pages has deployed from `main`:

**https://revintellect.github.io/r1-hungry-caterpillar/**

The workflow in [`.github/workflows/pages.yml`](.github/workflows/pages.yml) deploys the repo root on every push to `main`. No tokens or repo secrets. First successful run after merge publishes the site.

If that first run fails with Pages not enabled, one Settings click unblocks it — **Settings → Pages → Source: GitHub Actions**. Not required tonight.

## Controls

| Input | Action |
| --- | --- |
| Tap / click the canvas | Start, or steer toward the tap |
| Arrow keys | Steer |
| Enter or Space | Start / restart |
| R1 `scrollUp` / `scrollDown` | Steer (device wheel) |
| R1 `sideClick` | Start / restart |

The playfield is the R1 screen: **240×282**. On a desktop browser the frame is centered on the page.

## Layout

| Path | Purpose |
| --- | --- |
| `index.html` | The entire game (markup, CSS, canvas loop) |
| `.nojekyll` | Tell GitHub Pages to serve files as-is |
| `.github/workflows/pages.yml` | Deploy from `main` |
| `AGENTS.md` | Agent operating notes |
| `CLAUDE.md` | Short Claude / BLAST brief |
| `HANDOFF.md` | Ultra overnight handoff |

No `src="/"`, CDN, or sibling-folder assets. Relative paths stay valid on a project Pages URL (`/r1-hungry-caterpillar/`).

## Out of scope

Do not add a bundler, backend, analytics, auth, or Applause material. Keep the game one file unless a real asset is required.
