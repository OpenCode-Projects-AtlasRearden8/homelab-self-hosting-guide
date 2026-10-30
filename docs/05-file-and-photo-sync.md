# Chapter 5 — File and Photo Sync

Time: one evening for files, one more for photos. Tools: the server, the family's devices. Corners cut so far: none, and tonight needs none either.

The family's digital life mostly happens in two places: *folders* (documents, school forms, the mortgage PDF) and *camera rolls* (the photos and videos that are, in the long run, the only part anyone cries about losing). This chapter puts both on the family server, on your terms, using two free tools that have carried households like yours for years.

The plan for tonight has a shape worth naming **files first, photos second** — files build the habit in an evening, while photos deserve the extra attention they take.

## Part one: the family folder, synced everywhere

**Syncthing** is the workhorse of home file sync: free, open-source, no accounts, no cloud in the middle. It keeps chosen folders *identical*, live, on every device you point at it — a change on one laptop appears on the server and on the other laptop within seconds, inventor to invoice.

### A quiet house rule first

Decide *where* the family folders live on the server before touching config — something like `/home/YOURNAME/family` holding `documents`, `school`, `projects`. One folder tree, shared by everything, named after drawer labels the family already understands. Renaming conventions later is the tax you pay for skipping this paragraph.

### Set it up

1. Install Syncthing on the server (Linux package or the official installer; a browser window called "Syncthing" opens its settings, and it lives there naturally).
2. Install the app on each family computer and phone; on phones it runs politely in the background.
3. On the server, add the `family` folder. Share it — Syncthing's sharing screen names each device by a short code — with each family device.
4. On every device, choose where the shared copy lands (`Documents/family` is popular) and accept.

That is the whole installation. From then on: add a document on the laptop, it appears on the server. Edit the school form on the phone, the server has it. The server quietly keeps a copy of the truth while the house lives its life.

### The three confessions, said early

- **A deleted file is deleted everywhere.** Sync copies the truth, and deletion is truth. That is *good* — it is how design should work — but it is why [chapter 8's backups](08-backups.md) are next in line after this chapter, not eventually.
- **The same file edited on two devices at once** makes two copies (one wins, one gets a "conflicted copy" name). In practice, a family mentioning this twice a year is normal; the files are honest about it, no silent data loss.
- **One folder per conversation** beats one giant folder. `school` and `documents` sync faster and are easier to share selectively than one vast `family-everything`.

## Part two: the camera roll

Photos are a different animal. Volume is big (tens of thousands of files grow up fast), phones upload on their own schedules, and the family's expectations come from the photo apps they already use — albums, faces, search, moments. Two honest paths exist, and both start on the server:

### Path A: the photo library app — Immich (the beloved choice)

**Immich** is a free, self-hosted photo library that behaves *very* like the mainstream apps: phone backups in the background, albums, face search, memories on birthdays. It is the reason many people build a homelab at all, and it has earned the affection.

It wants, more than the printers and wikis of the world, some machine muscle — the memory notes in [chapter 2's comparison table](02-picking-the-spare-device.md) exist largely for this part. On a laptop or mini PC from the last several years it runs happily; on a Raspberry Pi it will run but slowly, and search-by-face is the part that sulks. The tool also runs via Docker — the glossary explains containers in plain English — and its official install page walks it in a copy-paste way.

The setup story in short: install on the server, install the phone app for each family member, sign in, let each phone's camera roll back up over your home wifi overnight. Days later, the family gets the payoff — albums like `Christmas 2024`, search by name, and the odd feeling of seeing a photo from six years ago while brushing your teeth.

Two honest cautions, both from the software's own docs:

- Turn on the phone app's "delete from phone only after backup is confirmed" behavior. It is the difference between a sync and a guess.
- Immich's model *is* "back up the phone, then the phone is safe to clean." That is its job. If you want a *second* place photos live, that is chapter 8's offsite copy, which every path here needs anyway.

### Path B: the folder — photos as files, synchronized

If the family's photo expectations are modest — "photos live in folders named `2024-07-camping`" is a perfectly stable life — then Syncthing is *also* the photo tool: point a phone's camera-roll folder at the server (the Android app handles it well; iPhones prefer keeping folders, being cloud-shaped by design — an honest limitation, not a fault to troubleshoot).

This path is slower to search, faster to trust. Nothing indexes it, nothing can break it, and `cp` from a laptop works on it forever. Many careful families happily live in path B and only grow into path A when an album habit appears.

### Which path tonight?

The rule of thumb: **if someone in the house would be sad without face search or birthday memories, path A; if photos are a filing habit, path B.** There is no shame in B now, A later — the folders of B are exactly what Immich would manage anyway, and the camera roll does not care about your timeline.

## The phone question, answered plainly

Because it is asked every time: *the phone is the hard part.*

- **Android:** both Syncthing's app and Immich's app behave as promised — background uploads, do-not-disturb for the family's wifi hours. This is the easy case.
- **iPhone:** Apple wants photos to belong to the cloud, and it fights background ownership. Immich's iPhone app works, and its background behavior is the one wrinkle of the whole chapter — photos upload when the app opens or charges on wifi, not whenever the phone pleases. Set the family expectation accordingly ("plug in on the hallway shelf at bedtime"), and it is reliable for years. This is one of the honest trade-offs chapter 9 discusses — for an iPhone-only household, mainstream cloud photos are legitimately good insurance *in addition to* (not instead of) what you build tonight.

## Before you move on

- [ ] The family folders sync live between the server and at least two devices.
- [ ] A test file added on the phone appeared on the laptop within a minute of the wifi waking up.
- [ ] The camera-roll choice (A or B) is made, and the upload you watched with your own eyes is confirmed on the server.
- [ ] The delete-and-conflict rules of this chapter were explained to the family, once, without jargon.
- [ ] Chapter 8 is circled on the checklist, dated, and described in your notes as "non-optional now."
