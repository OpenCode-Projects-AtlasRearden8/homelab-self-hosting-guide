# Chapter 11 — The Glossary

Every word the book used and then explained in a hurry, collected here at dictionary pace. Cross-references point back to the chapter where the term earned its place.

**3-2-1** — The backup standard: three copies, two kinds of media, one offsite. Chapter 8 turns it into a family-sized plan.

**Backup drive** — Any USB drive whose full-time job is holding copy number two, and whose resting place is a shelf, unplugged, away from the machine it saves. Chapter 8, level 1.

**Bandwidth** — How much data your internet connection can carry per second, in both directions. Home upload speed (the direction your server sends to you) is the smaller one, which is why huge public traffic is not the family server's sport.

**Camera-roll sync** — The house agreement by which photos taken on a phone find their way to the server. Chapter 5 has the Android-easy and iPhone-polite versions.

**Conflicted copy** — What file sync creates when the same file is edited on two devices at once: both survive, one renamed, nothing silently lost. Chapter 5 introduces it with compassion.

**DHCP** — The router's automatic address-assignment habit. Handy for guests, wobbly for servers, which is why chapter 3 pins the server's address with a DHCP **reservation**.

**DHCP reservation (static lease)** — A note in the router: "this device always gets this address." Interior decoration only; nothing is opened to the internet by it. Chapter 3, step 3.

**Docker / container** — A tidy wrapper containing an app plus everything it needs, isolated from the rest of the machine, started and stopped as one thing. Immich from chapter 5 arrives in one; the glossary-level takeaway is "a lunchbox, not a renovation."

**DokuWiki** — A decades-old, free wiki whose pages are plain text files, installable without a database. Chapter 6's medium-size choice, and chapter 8's favorite thing to back up.

**Hostname** — The machine's human name (`family-server`), which your network translates into its number. Chapter 3 names it; the [starter checklist](10-starter-checklist.md) records it.

**HTTPS** — Web traffic in an encrypted envelope, marked by the padlock. Inside your own lane the certificates are simpler than the public internet's; you will meet the topic only in gentle form at the end of chapter 7.

**Immich** — A free, self-hosted photo library with albums and search that behaves like the mainstream apps. Chapter 5's Path A, and the reason many homelabs exist. Happiest on a machine with room to breathe (chapter 2).

**IP address** — A device's number on a network, like `192.168.1.42`. The only question is only ever *which* network: inside the home, or the whole internet.

**LAN** — The local (in-house) network — the couch, the printer, the family server. **WAN** is everything beyond the router.

**Nextcloud** — The "everything app" (files, calendar, wiki, contacts). Powerful, yellow-zoned in chapter 1; start with two features and no more.

**NAT** — The router's trick by which your whole family shares one public internet address, keeping inbound strangers out by structural deafness. The reason your green zone is green.

**Offsite copy** — The "1" in 3-2-1: a precious-data copy in another building — a relative's synced laptop, or a modest cloud tier. Chapter 8, level 2.

**Port** — A numbered door on a machine (a thousand doors per address). **Port forwarding** opens one of them to the whole internet; the phrase this book exists to retire. Chapter 4 says why, twice, kindly.

**rsync** — The copy command that copies only what changed: fast forever after the first time. Chapter 8's workhorse and chapter 7's messenger.

**Router** — The box that is your home network's only border with the internet. Its admin page is where reservations (chapter 3) live and where port forwarding (do not) lives.

**Server** — A computer whose job is to serve, quietly, to devices that already trust it. By the end of chapter 3, that word is allowed to mean your laptop in the corner.

**Static site** — A website made of plain files: no accounts, no forms, no database — the green-zone pet of chapter 7.

**Syncthing** — Free, account-less folder sync between your own devices. Chapter 5's Path B workhorse and part one's evening.

**Tailscale** — The friendly VPN lane recommended by chapter 4: a free personal tier, an app per device, and a member list that *is* the family's access policy.

**VPN (as used here)** — A private road ending inside your home network, invisible to strangers, open only to devices you invited. Not the commercial "watch another country's streaming" product; the family's private lane. Chapter 4, the whole point.

**Wiki** — One shared place for the family's how-to life: recipes, wifi notes, house manual. Chapter 6, in three sizes.

**WAN** — See LAN. Everything that is not the couch.

**The lane** — This book's affectionate name for the private VPN from chapter 4. When the [checklist](10-starter-checklist.md) says "the lane means strangers never see the door," this is the it.
