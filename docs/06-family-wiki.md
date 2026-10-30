# Chapter 6 — The Family Wiki

Time: one evening to standing, then a pleasant trickle of content whenever it pleases you. Tools: the server, your normal computer.

Every family has a private encyclopedia that does not exist anywhere: how the smoke detectors behave, the third-generation pancake recipe, which plumber to call and which one you *vowed* never to call again, the wifi password in plain words for guests, the "which cable is which" guide to the TV. It currently lives in a group chat where the search function goes to die, or in one person's memory, where it leaves when they travel.

The family wiki is where those notes go to live properly: one page, on the server, reachable by the whole family through the private lane from [chapter 4](04-remote-access-without-scary-exposure.md) — findable, linkable, and *owned by nobody's phone*.

## Pick your shape: three happy sizes

A wiki is not one product. It comes in three sizes, and matching the size to your family — not to the internet's enthusiasm — is the whole decision:

### Small: a folder of notes (the start-small choice)

Here is an under-advertised truth: **a shared folder of Markdown files is a wiki.** You already installed folder sharing in [chapter 5](05-file-and-photo-sync.md). Make a folder called `wiki/`, write files like `wifi-and-guests.md`, `recipes/pancakes.md`, `house-how-to.md`, and they sync to every family computer — readable, searchable, backed up by the same machine as everything else.

- **Best when:** the family's readers write with plain apps, edit rarely, and mostly *read*.
- **Effort tonight:** ten minutes. This is genuinely a full implementation, not a placeholder; some families happily live here forever, and the "real wiki" upgrade below keeps the same content.

### Medium: a real wiki app — DokuWiki (the house favorite)

**DokuWiki** is decades-stable, free, plain-text wiki software with a browser editor the whole family can use, accounts for who can edit what, and a search box that treats your fifty scattered life-notes like a proper encyclopedia. It needs no database — its pages are plain text files on disk, which is a gift two chapters from now, because it means [backups](08-backups.md) are literally "back up one folder."

Install it on the server (its official page walks it for your Linux flavor; on Debian-family machines it is even in the package listings), create the family logins, and the home page becomes a table of contents as links accumulate. First pages worth planting, in order of proved family usefulness:

1. **Wifi and guests** — the password, in plain English, politely worded.
2. **Recipes** — one page per dish, the amounts *as actually made last time*.
3. **The house manual** — smoke detectors, the water shutoff, which breaker is which (photos welcome; wiki pages hold images fine).
4. **Repairs and people** — who you call, when, what they said.
5. **How to ask for what you need** — "photos go here," "print jobs wait here," the family's own how-the-server-works page, linked from the home page.

### Large: Nextcloud and its cousins — deliberately deferred

The "everything apps" bundle a wiki with files, calendars, and contacts. They are excellent software and chapter 1 puts them in the yellow zone on purpose: each extra feature is one more thing to patch and one more thing to break. If a family wiki is the need, a single-purpose tool is easier to keep healthy.So start small; a wiki that stays alive beats a suite that stays half-on.

## The setup, in plain steps (medium size)

1. On the server, install DokuWiki by your distro's usual method and open its address in a browser — `http://family-server/dokuwiki` or the address its installer names.
2. Follow its start page: create the admin account, then one account per family member who will *write* (readers can use a read link without accounts — nothing to remember).
3. Plant the five starter pages above. Ten minutes total; the structure teaches more than any tutorial.
4. Bookmark each reader's page. The family's bookmarks now live across the private lane — they work at home and at grandma's exactly the same.

## The habits that decide whether it survives

The failure mode of family wikis is not technical; it is the six-week note-decay. Three small habits keep it alive:

- **Ask, don't store.** Any time a chat message answers a repeated question ("what's the wifi?"), the answer *also* goes to its wiki page, and the reply becomes "it's on the wiki — second page down." Six weeks of this, and the wiki becomes the reflex.
- **One page per recurring thing** and link pages that mention it. A wiki is not organized by being organized; it is organized by *links*.
- **The monthly five** (piggyback the update ritual from [chapter 3](03-the-first-evening.md)): skim all pages, fix anything stale. Notes rot quieter than food; the skim is the refrigerator light.

## What a wiki family is like, later

Around month three, some pleasant symptoms appear: the kids ask the wiki for the printer steps instead of shouting; a recipe survives a spilled-on page; the plumber question stops depending on who remembers. And — quietly — the wiki becomes evidence of something bigger: the family now has a *place* its common life lives, and it is a place nobody can take with a policy change. That is the entire promise of this book, made tangible.

## Before you move on

- [ ] The wiki exists — folder or app — and you can find `wifi-and-guests` on the first try.
- [ ] At least one other family member has edited a page (small victory, real adoption).
- [ ] The monthly skim is on the starter checklist alongside update night.
- [ ] The five starter pages are alive, even if just stubs with good intentions.
