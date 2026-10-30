# Chapter 7 — Hosting a Small Website

Time: one evening, most of it spent making the page. Tools: the server, any text editor. This is the chapter where the homelab gets a *front porch*.

Somewhere in the back of your plans is a small site: the family's holiday letter, a recipe page for the reunion, a portfolio, a little guide like the one you are reading. Hosting it yourself is one of the most pleasant self-hosting jobs — calm, tiny, cheap — and it teaches the same skills the pros use, at garden scale.

## Why "static" is the magic word

A **static site** (glossary entry: pages that are plain files, no accounts, no forms, no database) is the web's sensible pet:

- **Nothing to attack with profit.** No logins, no comments, no submissions. A static site at home in the green zone is about as threatening as a framed photo.
- **Nothing to update for security.** There is no software to patch, only pages to edit.
- **Nothing to lose sleep over.** If it falls over, you rebuild it by copying the files again.

This is why chapter 1 put static hosting in the green zone sight-unseen, and why this chapter has no lock icon anxiety. Workflow, in the friend-possible version:

1. **Write pages in Markdown** — the friendly format this book itself is written in.
2. **Generate HTML** with a build script (the guide you are reading has one in its `scripts/` — a fine starter; every static generator works here, and there is no obligation to use a famous one).
3. **Copy the output to the server.** A `cp` or the sync from [chapter 5](05-file-and-photo-sync.md) moves the files; a small helper web server serves them.

## Serving the pages on the server

Linux ships with everything needed. Put the built files in a folder — `/home/YOURNAME/site` — and hand the job to the web server that is already part of most systems (or one `apt install` away):

```bash
# from the machine that holds the files
rsync -av site/ family-server:~/site/
```

then, on the server, point your web server's config at `~/site`. The exact stanza depends on which server is installed, and both major ones document it in a five-minute recipe — the only choice that matters at family scale is "whatever is already installed."

Check it from your own laptop, inside the lane:

```bash
curl -s http://family-server/ | head -5
```

If your page's title comes back, the porch exists. Family members open it through the lane from [chapter 4](04-remote-access-without-scary-exposure.md) — from home and from anywhere, by the same address, with nothing exposed publicly.

## The public question, answered honestly

"So... can the *whole internet* see my site?" Three truthful answers, in order of how much life you want:

1. **Probably not on purpose.** A static site has no accounts; the scary stuff from chapter 1's red list does not exist here. If your family site wishes to be public, it may be, honestly. The part to keep in mind is traffic: a home connection is sized for a household, not a crowd, and a sudden spike (a link from a big site) can exhaust your connection's patience.
2. **The polite bridge exists.** If you want a genuinely public site without the traffic worry, a "tunnel" service in front of your home server can look after it — some are free, all add someone else's software to your chain of trust, and they belong to the yellow-zone habits more than green. It works; it is a fine later-evening project; it is not tonight's homework.
3. **The cloud option is not defeat.** For a truly public, always-on, "my personal brand" site, GitHub Pages and similarly free hosts exist for this exact job, cost nothing, never wake you, and pair perfectly with the same Markdown workflow (your files in a repository, their machines serving the world). Chapter 9 gives this its endorsing voice. Home for the *family* pages, cloud for the *world-facing* pages is a completely honorable hybrid.

## What to put on it, when you cannot decide

Family-scale sites that hold up over years share one trait: they answer questions people actually have.

- **The reunion page** — date, dishes list, parking answers, last year's photos.
- **The how-to page** —— your wiki's public half, embedded — (printer instructions, wifi answers) so guests can read it without touching the wiki.
- **The portfolio** — your writing, craft, resume, gallery. Static pages were born here.
- **The kindness page** — the neighborhood tool lending list, the classroom volunteer sheet.

Keep it to a handful of pages. A site with five pages you love beats thirty pages you maintain out of guilt.

## The two habits of a happy site

- **Rebuild before you toast.** Any time the *source* pages change, the build step re-runs, then the sync. The one-line build in this book's own repo (`python3 scripts/pipeline.py`) is the whole ritual — the reminder lives on the [starter checklist](10-starter-checklist.md) with everything else.
- **Back up the source, not just the output.** Markdown sources are small and priceless; back them up by chapter 8's rules like any other family data. The generated HTML is replaceable; the *writing* is not.

## Before you move on

- [ ] The site builds from Markdown, and the built pages copied to the server.
- [ ] `curl` from a second machine (or your phone on the lane) shows the page.
- [ ] You consciously chose this site's audience — family-and-lane, or public — rather than drifting into it.
- [ ] The source Markdown lives somewhere chapter 8 already protects.
