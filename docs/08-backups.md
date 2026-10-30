# Chapter 8 — Backups That Actually Happen

Time: one evening to establish, five minutes a season to keep alive. Tools: one USB drive (or a taught-to-you second location). Readiness, honestly assessed: after chapter 5, the family server now holds the camera roll — so this chapter became non-optional the moment that sync first worked.

The old laptop revival guide opens its whole world with a backup chapter, and the Raspberry Pi guide has a whole-card companion for its shape of machine. This chapter is the family-server volume of the same religion, with the same commandment: **a backup that has never been restored from is a wish, not a backup.**

## The rule that governs everything: 3-2-1

The whole of backup thinking compresses into three numbers every serious institution uses and every family survives by:

- **3 — three copies** of anything you would hate to lose (the original on the server, plus two).
- **2 — two different kinds of media** (so a dying drive brand, or a fire, or a spilled glass is not a coordinating event).
- **1 — one copy somewhere else** — another building, another town. Fire, flood, and theft do not respect your hallway.

That is the standard. It looks expensive and sounds professional, but note what it does *not* say: it does not say "buy a NAS," it does not say "mount a rack." A family server, one USB drive in a drawer, and one synced folder to a relative's house satisfies all three numbers with hardware purchased for the price of a family dinner.

## Start by dividing your data with the two-question test

Not everything deserves three copies. Run each thing on the machine through:

1. **If this vanished right now, would anyone cry?** Photos, personal documents, the wiki pages, the site sources: yes. The operating system, the installed apps, the recovery notes: no (they rebuild from their own docs — including chapter 3's `server-notes.txt` recipe, which is exactly why that note exists).
2. **If it changed silently without you noticing, would that be worse than losing it?** (Financial and medical papers; anything other humans rely on.) These rate *extra* scrutiny, per chapter 1's red list.

The family's "yes-to-crying" list, in the commonest shape: the family folder tree from [chapter 5](05-file-and-photo-sync.md), the photo library, the wiki folder (or DokuWiki's pages folder for the medium build — the fact its pages are plain text makes this pleasingly easy), and the website sources from chapter 7.

## Level 1: the local copy (tonight)

The first copy is the simplest and the one everyone skips: **one USB drive, one command.** Plug the drive into the server, and give it the work:

```bash
rsync -av ~/family /media/YOURDRIVE/backup-$(date +%m)
```

rsync (glossary entry: the copy tool that only copies what changed) makes the first run slow and every later run fast. Schedule it weekly — the how-to is in most distros' task-scheduling docs, and the starter checklist keeps a line for the day of the week — and the drive lives on the shelf, *unplugged* except on backup day. A backup drive that is always plugged into the machine it backs up is a single point pair, not a strategy; ransomware, lightning, and brownouts treat them as one address.

Notes to keep these honest:

- Give every run a **dated folder name** — the `$(date +%m)` above does it — so mistakes last month do not overwrite this month.
- **One drive, two shelves.** If the budget allows, a second USB drive that swaps between the server and a relative's house is a beautiful, boring tradition.

## Level 2: the offsite copy (the next weekend, or tonight if you like)

The "1" in 3-2-1 with *zero* extra hardware, using tools you already own:

- **A folder sync to a relative's house.** Install the [chapter 4](04-remote-access-without-scary-exposure.md) lane app on a family member's machine in another town, then share the family folder with it via [chapter 5](05-file-and-photo-sync.md)'s sync. Their laptop becomes the offsite copy, silently, on their schedule. This is the poor household's finest tactical move, and the relative gains free family photos as rent: everyone should be so lucky.
- **A cloud folder as the designated courier.** One modest cloud plan holding the *precious* subset — photos and documents, not the whole server — is a perfectly mainstream and honest offsite answer, chapter 9's whole theme. The family server keeps the big, free, personal copy; the cloud keeps the irreplaceable subset. Two homes for the family data beats one proud server with one drive.

Pick whichever offsite copy a family will actually maintain; both satisfy the "1." The mortal enemy of backups is not the plan, it is the plan's retirement date — so the next section is not optional either.

## Level 3: the restore rehearsal (ten minutes, once a season)

Here is the ritual that separates real backup from backup theater, and it is genuinely ten minutes once a season:

1. Pick **one file** — a real one, at random. Delete it from its home.
2. Restore it *from the backup drive*, using the drive's own contents, with no cleverness.
3. Open the file. Confirm it is the real thing.

That is it. If step 2 fails — and one season in three years, it will — you found out in a season with a drill, not in a tragedy with a data-forensics mood. Write the drill on the [starter checklist](10-starter-checklist.md), draw a tiny sad face next to each completed season (the lowest-stakes ritual in this book, the highest-value one).

And when the wiki, photos, and files all rehearse cleanly: put the *server note* through the same drill. A server rebuilt from `server-notes.txt` plus a restored data folder is back in business in an afternoon, and most of that afternoon is dinner.

## Before you move on

- [ ] The "would anyone cry" list is written down, and it is short.
- [ ] Level 1 ran once, and a restore of one file from the drive succeeded by hand.
- [ ] The offsite copy exists — a relative's synced laptop or a modest cloud plan — and you know which.
- [ ] The seasonal restore rehearsal is on the checklist, dated, with room for three years of sad faces.
