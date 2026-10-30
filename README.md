# The Family Self-Hosting Guide

A plain-English, friend-paced manual for gently self-hosting your family's tech at home — what is safe to host, which spare device to pick, file and photo sync, a family wiki, a small static website, remote access that never opens a scary door, backups, and the honest chapter on when plain cloud is simply the better choice.

Published as a free resource by [Asdale Dynamics, LLC](https://dylanasdale.github.io), the beginner-friendly AI education project of author Dylan Asdale.

- One evening per chapter, terminal steps spelled out, no jargon left unexplained.
- Security reduced to one idea you can hold: *who can reach the thing, from where, with what.*
- No bashing of cloud services; a full chapter on when the cloud wins fair and square.

## What is inside

- **docs/** — the guide itself, one Markdown file per chapter. `00-read-this-first.md` is front matter; the numbered chapters run 1–11:
  1. What Is Safe to Host at Home (the traffic-light map, sorted by reachability)
  2. Picking the Spare Device (old laptop vs mini PC vs Raspberry Pi, with decide-this-tonight quiz)
  3. The First Evening (updates, hostname, DHCP reservation, the sleep cure, the server note)
  4. Remote Access Without Scary Exposure (a private VPN lane, not port forwarding)
  5. File and Photo Sync (Syncthing for folders; Immich or plain folders for the camera roll; the honest iPhone section)
  6. The Family Wiki (folder-of-notes, DokuWiki, and why the everything-app waits)
  7. Hosting a Small Website (static pages, served at home; the public options, honestly priced)
  8. Backups That Actually Happen (3-2-1 in family size, plus the seasonal restore rehearsal)
  9. When Plain Cloud Is the Better Choice (the hybrid household table; zero guilt)
  10. The Starter Checklist (printable, evening-by-evening, boxes and sad faces)
  11. The Glossary (every term, at dictionary pace)
- **scripts/pipeline.py** — a standard-library-only static site builder. Converts the chapters into a polished offline-friendly HTML site: chapter pages with sidebar navigation and prev/next pagers, a landing page, and a single "whole book" page for print or Ctrl+F. `--check` lints links, anchors, and structure.
- **tests/test_pipeline.py** — unit and integration tests for the converter, builder, CLI, docs lint, and repo hygiene (secret-pattern scan, exact MIT LICENSE line, README credit).
- **site/** — the generated site (built locally; not committed).

## Quick start

Read it as plain text:

```bash
less docs/00-read-this-first.md
```

Or build the HTML site (Python 3 standard library only, no installs, no network):

```bash
python3 scripts/pipeline.py          # build docs/ into site/
python3 scripts/pipeline.py --check  # lint the docs (links, anchors, structure)
```

Then open `site/index.html` — no server needed; the site makes no external calls, so it works offline and from `file://`.

Run the tests:

```bash
python3 -m unittest discover -s tests
```

## How it complements the companion guides

This guide is shelf-mates with two other friend-paced manuals and deliberately does not repeat them:

- **The Raspberry Pi First Project Guide** — owns SD-card flashing, kit shopping, and four single-purpose Pi projects; this guide covers the whole-family server thinking around it.
- **The Local AI Handbook** — owns running private AI models locally, models and memory; our chapter 1 tells you *whether* that belongs on the family server at all.
- **The Old Laptop Revival Guide** — owns wiping an old laptop and Linux install day, plus its backup-first philosophy; our chapter 3 starts where install day ends.

All are (or will be) free, MIT-licensed, and readable in full at [dylanasdale.github.io](https://dylanasdale.github.io).

## License

MIT — `Copyright (c) 2026 Asdale Dynamics, LLC`. Copy it, share it, tinker with it.
