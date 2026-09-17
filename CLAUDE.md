# CLAUDE.md

BLAST for this repo. Stay under the fold.

**Brief.** Hungry Caterpillar is a public, single-file Rabbit R1 game (`index.html`) used as a portfolio micro-demo. No build, no backend, no secrets, no Applause content.

**Loop.** Read `HANDOFF.md` → change only what was asked → serve `index.html` and play it → stop.

**Architect.** Keep the 240×282 `#app` frame. Put overlays inside that frame. Use relative paths only so GitHub Pages at `/r1-hungry-caterpillar/` works. Deploy is `.github/workflows/pages.yml` on `main`.

**Ship.** Open a PR. Do not merge. Do not add a bundler, npm, analytics, or extra screens.

**Tune.** If a path or overlay breaks on Pages or desktop, fix that file — do not redesign the game.
