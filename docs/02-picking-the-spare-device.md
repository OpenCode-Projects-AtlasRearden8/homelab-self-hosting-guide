# Chapter 2 — Picking the Spare Device

The best home server is usually already in your house, resting. This chapter turns "spare device" from a vibe into a decision: what each kind of machine is secretly great at, what it will struggle with, and a short quiz to settle it. The rule that governs everything: **one quiet job per machine.** A server that syncs files, holds photos, and runs one wiki is a pet; a server that hosts five communities, two websites, and a media farm is a hobby that eats evenings.

## The three usual candidates

### The old laptop (the quiet champion)

If there is a functioning laptop in a drawer — slow is fine, even six-plus years old is fine — it is very likely the right choice, and here is the reason nobody advertises: **it has a battery.** A home server's worst enemies are power cuts and the electricity flickering at 2 a.m. when Linux is mid-update. A laptop absorbs a blink the way a dike absorbs a puddle — and it rides through a two-minute power cut at 2 a.m. while Linux is mid-update, on hardware you already own, without a single purchase.

Laptops also bring a built-in screen and keyboard for setup days (priceless), a display that only lights when needed, and a fan that — unlike a PC tower — does not negotiate below 40 watts.

- **Born to do:** file sync, the family wiki, a static website, a photo library for a modest collection, print sharing.
- **Struggles with:** heavy photo-AI indexing on huge libraries, multi-user video streaming at peak, compounding roles; old small drives. Pair it with a USB drive for space.
- **Watch out for:** its "sleep on lid close" default (chapter 3 fixes that in one minute), and dented hinges that make it happier lying flat.

If the laptop route is yours, the Old Laptop Revival Guide owns the wipe-and-install in careful detail: its chapter 3 on picking a friendly Linux and — even more important — its *backup-first* chapter 1, which you should read before politely erasing anything. This book picks up where that install day ends.

### The mini PC (the grown-up choice)

A used small desktop box (the kind offices retire by the pallet) or a budget new mini PC is the laptop's steadier cousin: more powerful per dollar, no battery, no lid problems, easier to add a big drive. It is the right machine when the photo library is genuinely large or several green-zone jobs happen at once.

- **Born to do:** everything the laptop does, faster, with more room to grow.
- **Struggles with:** power cuts (no built-in battery — if outages matter to you, a small battery brick is the classic companion, and it belongs to the backup conversation in chapter 8).
- **A hidden upside:** a tiny-footprint machine sips power — a good one idles below the laptop's average.

### The Raspberry Pi (the charming specialist)

A Pi is wonderful *if* the job is modest and single-purpose: a file drop, a photo frame server, a tiny website. It is also the best-documented beginner computer on earth — and the Raspberry Pi First Project Guide exists precisely to walk your first SD card, kit shopping, and four delightful starter projects. If a Pi is your hardware, read that guide's setup chapters first; this book's chapters still apply afterwards, with one addition: that guide's own backup chapter names a Pi-specific shape (the whole-card clone) that pairs nicely with our chapter 8 rules.

A Pi is *not* the right choice as the family's everything-server: photo libraries indexed by AI and busy many-device sync ask for more memory than most boards offer. Small corner of the homelab: yes. Whole homelab: the laptop or mini PC.

## The honest comparison

| Question | Old laptop | Mini PC | Raspberry Pi |
| --- | --- | --- | --- |
| Battery ride-through of power blips | built-in | none | none |
| Ready screen + keyboard for setup | yes | usually no | usually no |
| Power use when idle | modest | low | very low |
| Space for big photo drives | add a USB drive | easy inside | a USB drive again |
| Suits the whole "family server" job | yes, sweet spot | yes, most headroom | partial — one small job |
| Cost to you today | possibly $0 | used price of a lunch | kit price from the Pi guide |
| The thing that will surprise you | sleep mode | no battery backup | not enough RAM for photo AI |

## The two-minute decision quiz

Answer honestly:

1. **Is your photo collection under about 50,000 pictures and you do not need AI magic on it?** Then the laptop handles chapter 5 comfortably. Above that (or you want "search my photos by who is in them"), lean mini PC for the RAM and disk headroom.
2. **Will more than about six humans sync to it?** Two laptops' worth of usage is laptop-trivial; a whole extended family is mini-PC-shaped.
3. **Does the power go out at your place more than a few times a year?** That nudges any choice toward a laptop — or toward adding a small battery brick to whatever you picked.
4. **Is a Pi already on your shelf, powered by enthusiasm?** Then give it the single-job treatment and let chapter 7's website or the wiki live there, while a laptop (if one can be found) takes the files.

If the quiz cannot decide, the tiebreak rule is embarrassingly simple: **take the machine you already own and start.** Chapter 3's setup is identical on all three, and any of them can do the green-zone list from chapter 1. A homelab built on a slower-wrong choice and finished beats an ideal choice that never starts.

## One quiet job per machine, revisited

Notice how the three candidates each want one personality:

- The *laptop* is the family sync-wheel and wiki.
- The *mini PC* is the photo library headliner.
- The *Pi* is the project specialist next to the TV or in the bookshelf.

Every "should I also host X on it?" question stays answerable while each machine keeps one speaking part. It is the difference between a homelab you administer and a shelf of friendly appliances you occasionally feed.

## Before you move on

- [ ] You have picked a machine (or borrowed one to try), and know its one quiet job.
- [ ] If it is a laptop, its power adapter found the server corner.
- [ ] If it is a Pi, the Raspberry Pi First Project Guide's shopping and SD-card chapters are on your list.
- [ ] Any "bigger than this" ambitions are parked with a date to revisit, not a shopping cart.
