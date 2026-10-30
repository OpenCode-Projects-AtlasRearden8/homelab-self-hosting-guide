# Chapter 1 — What Is Safe to Host at Home

Self-hosting has a reputation problem. Half the internet says it is an avalanche of port forwarding, SSL certificates, and Russian botnets; the other half says you are negligent if your photos touch a data center. Both are exaggerations, and both evaporate once you replace the vague question — *"is self-hosting safe?"* — with the only question that actually matters:

> **Who can reach the thing, from where, with what authentication?**

That is the whole security model. Not "what kind of server is it," not "what brand of software," simply *reachability*. A password vault bolted to the open internet is dangerous; a folder of scanned insurance papers that only your household's laptops can reach is not. This chapter is the map you will consult every time a new idea ("should I host my own...?") shows up — sorted not by software name, but by how exposed it makes you.

## The traffic light, sorted by reachability

### 🟢 Green — host freely, day one

These run *inside* your home network and are reached only by your household or through the private VPN lane we build in [chapter 4](04-remote-access-without-scary-exposure.md). Nothing here accepts connections from strangers, which means the classic internet dangers mostly do not apply.

- **File sync** between your own computers and phones (Syncthing- and folder-shaped; details in [chapter 5](05-file-and-photo-sync.md)).
- **Family photo library** with an album app the family can browse.
- **The family wiki** — recipes, instructions, the "where does the spare key live" note (chapter 6).
- **A static website** — generated pages, no accounts, no forms (chapter 7).
- **A media shelf** — a folder of home videos the TV can play.
- **Print sharing**, scanner drop-boxes, and similar household plumbing.
- **A private AI chat** on capable hardware, offline and un-logged — as long as you follow the Local AI Handbook's guidance on what a model can and cannot promise. If the spare machine is a small one, the Raspberry Pi First Project Guide's local-AI project covers the modest version.

Green things share a shape: **no public port, no strangers, no complaints.** If your homelab never grew past this list, it would already beat most cloud setups on both privacy and calm.

### 🟡 Yellow — host with habits, after chapter 4

These get one or two doors opened, or they tempt you to open some. They are fine with the habits from [chapter 4](04-remote-access-without-scary-exposure.md) firmly in place (VPN-first access, no raw ports, updates on a schedule), and they deserve a second look from the backup rules in chapter 8 before you lean on them.

- **Anything you sync beyond your own devices** — e.g., grandparent access to the photo library via the family VPN.
- **A game server** the kids and their friends use.
- **Nextcloud and friends** — the "everything apps." Powerful, but each feature is another thing to keep patched; start with two features you actually use.
- **Home-automation hubs.** These usually refuse all inbound connections by design — fine — but every smart bulb has its own opinions, and the hub's dashboard is tempting to expose "just for a week."
- **Document scanners and cameras writing straight to the server.** Safe until a shared device's credentials wander; rotate them when the router's manual sounds like a good bedtime story.

Yellow is not "avoid"; it is "hold the habits." The moment you skip the VPN-first rule for one yellow item, it silently becomes the red one below.

### 🔴 Red — do not host from home, or only with serious caution

Some jobs genuinely want data-center-grade constant attention or bring outsized risk when a stranger arrives. Skip these at home not because you are incapable, but because the payoff never justifies the vigilance:

- **Email.** The internet's mail servers judge you by your IP address and NTBD your reputation for years for a single misconfigured month. Self-hosted email is a specialist's hobby, not family infrastructure. Use a reputable provider; make it a small one.
- **Anything holding other people's data you are not personally responsible for.** The family photos are yours to lose; your friend's business invoices are not.
- **Financial or medical documents** — *unless* the server is green-zone reachable only. Even then, the [backup rules](08-backups.md) are not optional for this category.
- **A public "login and upload" site** with accounts for strangers. The day you let strangers create accounts, you are running a community, and communities need a professional-grade security posture.
- **Anything the ISP's fine print forbids**, or anything that needs to stay reachable during power cuts (unless you have battery backup to spare).

## How to read the map in real life

When a new idea appears, run it through these four questions, in order:

1. **Where does it listen?** Home network only, VPN lane only, or the open internet? (If you do not know, that is chapter 4's job to make obvious.)
2. **What happens if it is reached?** Blank file listing, someone's data, or an admin screen? The blast radius tells you the traffic light more honestly than the software's marketing does.
3. **Who maintains it?** You, on a machine that also hosts other things, at no extra cost, forever. Hosting more means maintaining more — the "one quiet job per machine" rule from chapter 2 keeps that load sane.
4. **What is the cloud alternative?** Chapter 9 exists so this question always has an honest answer, not a guilty one.

## The three habits that carry the whole system

Whatever you host, these three cover 90% of real-world risk, and each is already a chapter here:

- **Keep everything inside the private lane.** Chapter 4's VPN-first rule means "strangers on the internet" never even see the front door.
- **Run updates before you remember the name of the software.** Most breaches of home servers are old bugs that had patches for months. A monthly five-minute ritual (chapter 3) beats any antivirus.
- **Assume any disk can die any Tuesday.** Chapter 8's backup rules make that a shrug instead of a tragedy.

With the map in hand, the next decision is which machine takes the job — and the answer, almost always, is already in your house. That is chapter 2.

## Before you move on

- [ ] You can say out loud what "green zone" means for your own family (no ports, household only).
- [ ] You have picked the two or three green things your homelab would actually be *for*.
- [ ] Any tempting yellow idea you have is written down for later, not started.
- [ ] Email is staying with a reputable provider, guilt-free.
