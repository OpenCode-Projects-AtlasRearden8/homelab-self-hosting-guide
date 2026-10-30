# STATUS

Project: The Family Self-Hosting Guide
Owner: Asdale Dynamics, LLC
State: complete and verified (October 2026)

## What was built

A friend-paced, beginner-facing manual for gently self-hosting family tech at home, plus the tooling that turns it into a static HTML site. Built in this pass against the stated goal; the folder started empty.

- **docs/** (12 Markdown files: front matter + 11 numbered chapters):
  - `00-read-this-first.md` — audience, chapter map, how it fits with the companion guides, what you need, pacing.
  1. What Is Safe to Host at Home — traffic-light map sorted by *reachability* ("who can reach it, from where, with what"), green/yellow/red lists, four real-life questions.
  2. Picking the Spare Device — old laptop vs mini PC vs Raspberry Pi, honest comparison table, two-minute decision quiz, "one quiet job per machine."
  3. The First Evening — update habit, hostname, DHCP reservation, the sleep cure, the server-notes file, unique password.
  4. Remote Access Without Scary Exposure — why port forwarding loses to a private VPN lane; Tailscale as the beginner default (with the plain-WireGuard DIY route named); family adoption; a two-minute security posture and seasonal checklist.
  5. File and Photo Sync — Syncthing for the family folders (with delete/conflict confessions); photos via Immich (path A) or plain synced folders (path B); the honest iPhone section.
  6. The Family Wiki — folder-of-notes, DokuWiki (medium, no-database), deliberately deferring Nextcloud; five starter pages; anti-decay habits.
  7. Hosting a Small Website — static-site workflow (write Markdown, build, copy), serving on the server, and the three honest answers to "can the public see it?"
  8. Backups That Actually Happen — 3-2-1 in family size, the "would anyone cry" sorting test, local USB-drive level, offsite level (relative's synced laptop or modest cloud tier), the seasonal restore-rehearsal drill.
  9. When Plain Cloud Is the Better Choice — honest trade accounting, the cloud-wins list (email, iPhone-heavy photo households, must-never-be-down), the hybrid household table, a four-question decision test.
  10. The Starter Checklist — printable, evening-by-evening task checkboxes, plus monthly/seasonal/yearly keep-alive rituals.
  11. The Glossary — every term used, at dictionary pace, with chapter back-references.
- **scripts/pipeline.py**: standard-library-only static site builder (no installs, no network). Produces a landing page, polished chapter pages with sidebar nav and prev/next pagers, a single-page "whole book," and a light/dark/print-aware stylesheet. `00-` stems are front matter, so on-page "Chapter N of 11" labels match in-book references. CLI: `--docs/--out`, `--from-md FILE`, `--check`.
- **tests/test_pipeline.py**: 43 tests — converter (headings/anchors, inline markers, escaping, links, lists, task lists, tables, fences), lint rules, builder, CLI, reproducible builds, a well-formed-HTML proof over the real generated pages, docs-plan/theme checks, and repo hygiene (secret-pattern scan, exact MIT line, README credit, allowed top-level files).
- **README.md, LICENSE** (MIT, exactly "Copyright (c) 2026 Asdale Dynamics, LLC"), **.gitignore** (site/ and `__pycache__` not committed).

Companion-guide boundary (per the no-repeating rule): the Pi kit/SD-card/projects live in *The Raspberry Pi First Project Guide*, laptop wipe + Linux install day and backup-first philosophy in *The Old Laptop Revival Guide*, and running private AI models in *The Local AI Handbook*. Those are referenced by name in prose (never as relative links, so cross-repo links can't break), and only the family-server angle is developed here.

## How to run it

```bash
python3 scripts/pipeline.py            # build site/ from docs/
python3 scripts/pipeline.py --check    # lint docs (links, anchors, structure)
python3 -m unittest discover -s tests  # run the test suite
```

Open `site/index.html` in a browser (works offline and from `file://`; no external requests).

## Verification results (run in this folder)

- Python 3.13.5
- `python3 scripts/pipeline.py --check` → "Checked 12 markdown files: clean"
- `python3 scripts/pipeline.py` → "Built 15 files into .../site" (13 HTML pages + style.css + index)
- `python3 -m unittest discover -s tests` → 43 tests, OK (0 failures, 0 errors)
- html.parser tag-balance check over all 13 generated pages → 0 problems (part of the suite)
- Two consecutive builds produce identical output manifests (reproducibility test)
- Internal-link audit: every `[...](x.md#anchor)` resolves to a real file and heading slug (part of lint + suite)
- Non-ASCII sanity sweep over docs → no stray non-English fragments
- Secret-pattern scan across docs/scripts/tests/README/LICENSE → 0 matches
- No paid products, accounts, or API keys assumed anywhere in the content
- Git initialized with the existing configured identity (Dylan Asdale); single commit, nothing pushed, no remote

## Known gaps

- `site/` is a generated artifact and is gitignored; re-run `python3 scripts/pipeline.py` after any docs change.
- No full-text search page; use `site/book.html` with browser Ctrl+F (deliberate: zero JavaScript, zero tracking).
- The Markdown converter is a purposeful subset (no images, footnotes, or definition lists); conventions are enforced by `--check` and tests rather than silently rendered.
- Tool specifics (Tailscale, Syncthing, Immich, DokuWiki) are described at the level of the mental model and official vendor install flows; exact menu paths and version numbers are intentionally not pinned so the chapters age gracefully.
- The public-site "tunnel bridge" option in chapter 7 is named but not walked through step-by-step (deliberately deferred as a later-evening, yellow-zone topic).
- The seasonal/restore scripts are described as manual rituals rather than shipped cron files — a possible future addition if wanted.
