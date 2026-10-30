# The Family Self-Hosting Guide — Read This First

Somewhere in your house there is a machine doing very little: a laptop in a drawer, a mini PC that outlived its monitor, a hand-me-down that hums politely in a corner. Meanwhile the family's photos live in an app that changes its layout every spring, the recipes live in a group chat nobody can search, and the only copy of the wedding video is one cloud account and a lot of luck.

This book is about giving that spare machine a quiet, meaningful job. Not a data center, not a career, not a rack whirring in the hallway — just a small home server that holds your files, your family wiki, and maybe a little website, and lets you reach it from anywhere like it is sitting next to you.

The promise: every chapter is a single cozy evening or less, written the way a friend would explain it. No condescension, no fear-mongering, and — when self-hosting is the wrong call — we say so plainly in [chapter 9](09-when-plain-cloud-is-better.md).

## Who this guide is for

- You are comfortable installing an app and following steps in a terminal when they are spelled out, but you do not want to become a system administrator.
- You have (or can borrow or buy cheaply) one spare device: an old laptop, a mini PC, or a tiny single-board computer.
- Your "users" are real people — a partner who will not install anything, kids on school tablets, a parent across town — and the setup has to survive their normal.
- You want your photos and files to belong to you, but you would like honest guidance, not an ideological war against companies.

## What this guide covers

1. **What is safe to host at home** — a traffic-light map, so you start with decisions you will never regret.
2. **Picking the spare device** — old laptop, mini PC, or tiny board; what each is secretly great at.
3. **The first evening** — getting the base trustworthy: updates, a fixed address, no surprises.
4. **Remote access without scary exposure** — the one chapter that keeps everything else safe.
5. **File and photo sync** — the family's folders and the camera roll, on your terms.
6. **The family wiki** — recipes, wifi notes, the good chili recipe, finally findable.
7. **Hosting a small website** — static, calm, and surprisingly polite to run.
8. **Backups that actually happen** — because a server with no backup is just an anxiety object.
9. **When plain cloud is the better choice** — the honesty chapter, and the most-useful one.
10. **The starter checklist** — a printable companion for the whole book, evening by evening.
11. **The glossary** — every term, in plain English.

## How this fits with the companion guides

This guide is one of a small shelf of friend-paced manuals, and they are designed to lean on each other without repeating:

- **The Raspberry Pi First Project Guide** — if you choose a Raspberry Pi as your spare device or want small, single-purpose Pi projects (photo frame, print server, pantry screen), that guide handles the SD card and the four starter projects. Read its shopping and setup chapters first, then come back here for the server-side thinking.
- **The Local AI Handbook** — if the spare machine is destined to chat back with a private AI model, that handbook covers models, memory, and privacy far better than a chapter could here. This book's [chapter 1](01-what-is-safe-to-host.md) tells you *whether* that belongs on the family server at all.
- **The Old Laptop Revival Guide** — if your spare device is an old laptop, that guide owns the wiping and Linux installation in detail; our [chapter 3](03-the-first-evening.md) starts right where its install day ends, and its backup chapter pairs with ours.

Cross-references in these pages name the guide and its chapter in text rather than links, so you can read any of the books offline, printed, or alone without broken breadcrumbs.

## What you will need

- One spare device (chapter 2 helps you choose; "the one in the drawer" is a fine place to start) and its charger.
- Your normal computer and phone for setup.
- An evening or two per chapter, coffee optional but traditional.
- No paid subscriptions, no new hardware purchases required, no soldering.

## How the chapters pace themselves

Each chapter opens with the time it takes and the tools it needs, and closes with a small "before you move on" list mirroring the [starter checklist](10-starter-checklist.md). Nothing here assumes the previous chapters were done perfectly — skip ahead, come back, or stop at a chapter that already solved your problem. A half-built homelab that syncs three folders is a success; a plan to eventually build the whole thing is not.

## A note on tone and safety

Everything here stays in "family tech" territory: files, photos, notes, small websites. Nothing in this book is medical, legal, or financial advice, and the family server is never the right place for anything a stranger should never see. Privacy comes from *who can reach it*, and that single idea — learned in [chapter 4](04-remote-access-without-scary-exposure.md) — does more weeks of good than any firewall table ever will.
