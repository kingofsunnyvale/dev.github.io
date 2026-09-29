# Memory

2026-09-29 — Cube diagonal direction corrected
---
- Samarth requested upper-left-to-lower-right rotation and authorized a local commit without pushing. Changed the rotation axis in `devsamarth_v3/src/App.css` from `(1, 1, 0)` to `(-1, 1, 0)`.
- Local Chromium measurements confirmed the front face moves right and down. The cube is still 22px with a 10-second rotation, and reduced motion disables the animation.
- `bun run build` and the CSS diff-check passed; local browser inspection reported no page errors. The task's Bun/Vite server on port 5180 was stopped. Existing edits in `src/App.tsx` and `src/pages.tsx` belong to the user and are excluded from this commit.

2026-09-28 — Cube motion refinement
---
- Samarth requested a smaller cube with a faster diagonal rotation. Updated `devsamarth_v3/src/App.css`: 22px sides (previously 26px), a 10-second loop (previously 18 seconds), and `rotate3d(1, 1, 0, ...)` for diagonal-axis rotation.
- Adjusted face depth to 11px and recentered the smaller cube and ground line. The shared animation applies across all pages.
- Verified `bun run build` and CSS diff-check, inspected four rotation phases in local Chromium, and confirmed navigation, reduced motion, and zero browser errors. The local Bun/Vite server was stopped afterward. No tests added or commits/deployments performed.

2026-09-28 — Revamp complete and verified locally
---
- Bun workspace is configured at the repo root with one `bun.lock`; root commands forward to the app. Use `bun install`, `bun run dev`, `bun run lint`, `bun run build`, `bun run preview`, and `bun run deploy`.
- New app structure: `src/App.tsx` for shell/cube/navigation, `src/pages.tsx` for page bodies/Markdown, existing `src/content.tsx` for portfolio text/links, `src/posts/*.md` for writing, and `vite.config.ts` for Markdown loading/static route entries.
- White/grey NieR menu styling uses locally served IBM Plex Sans, a small CSS 3D cube, and a 320 ms jump before same-tab navigation. Reduced motion, keyboard focus, modified clicks, and browser history are supported.
- Blog supports YAML metadata, filename-derived dates/slugs, newest-first order, and GFM rendering. The template is an unpublished draft. Temporary verification posts were removed. Shared view counts remain deferred by Samarth.
- GitHub Pages still uses the existing gh-pages branch and `devsamarth.com`. Deploy adds `--nojekyll` because gh-pages excludes dotfiles by default. Builds emit real route entry HTML, `404.html`, `.nojekyll`, and CNAME.
- Verified `bun install --frozen-lockfile`, `bun run lint`, and `bun run build` (all exit 0). Scoped `git diff --check -- . ':!Website_Revamp.md'` passes; full diff-check only flags pre-existing whitespace in the user-owned brief.
- Local Bun-driven Chromium checks: main routes at 1440/390px, Markdown at 320px, no document overflow or page errors, cube reaches Y=0 before URL change, history/rapid clicks/Ctrl-click/keyboard/reduced motion work, and CV returns 200 PDF. Static deep links and refreshes returned 200; missing paths returned a styled 404.
- Final build excludes draft/template content and temporary preview posts. Screenshot files: `/tmp/opencode/website-revamp-desktop.png`, `/tmp/opencode/website-revamp-mobile.png` (ephemeral).
- Independent read-only reviewer (`ses_f14e6244effe9zEOPNhtlEf7HS`) found no critical or important issues, and one Markdown italics issue. Reproduced pixel-identical plain/emphasized text, then fixed `.markdown em` with `font-synthesis: style`; local screenshots confirmed visibly distinct italics. Fresh build, lint, and scoped diff-check passed after the correction.
- Verification servers on 5173 (Bun/Vite PID 188903) and 4173 (Bun static PID 194064) were stopped. Both background commands completed after the explicit shutdown.
- No tests added, commits, pushes, or deployments performed. The current execution record is in `docs/superpowers/plans/2026-09-28-website-revamp.md`.

2026-09-28 — Website revamp in progress
---
- Samarth supplied `Website_Revamp.md` and requested implementation: Bun, existing gh-pages deployment, white/grey NieR-inspired design, rotating/jumping cube, and Work/Products/Markdown Blog routes.
- Samarth explicitly deferred universal blog-view counts: “Hold off on the blog-view counts, just continue with the rest of the implementation”. No counter/backend work is in the active scope.
- No added tests; verify with Bun and local desktop/mobile browser checks. Do not commit or deploy; stop local servers afterward.
- App lives in `devsamarth_v3`; existing deployment is `gh-pages -d dist`, Vite base `/`, and `public/CNAME` is `devsamarth.com`.
- Existing `Website_Revamp.md` modifications belong to the user. Current biography, jobs, projects, resume, and social links are the migration's content source.
- Execution checklist: `docs/superpowers/plans/2026-09-28-website-revamp.md`.
- All three portfolio references and the supplied NieR screenshots were inspected. Desktop browser tool is disconnected; local Bun-driven Playwright is available from `/home/samarthdev/.bun/install/cache/playwright@1.58.2@@@1/index.mjs`, using cached Chromium headless shell 1208.

2026-09-28
---
- Markdown content in this workspace may use YAML front matter; Markdown tables require pipe syntax.
