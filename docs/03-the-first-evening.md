# Chapter 3 — The First Evening

Time: one relaxed evening. Tools: the device, its charger, your normal computer. Credit card: asleep in a drawer where it belongs.

The goal of tonight is modest and foundational: the machine gets a name, a fixed address inside your home network, working updates, the sleep-cure, and a backup copy of tonight's best work — a one-page note of what you did. Nothing here is dramatic; everything here is what makes chapters 4 through 8 boring later, which is the whole point.

If your spare device is an old laptop that still has whoever's old life on it — or you want to install Linux fresh — pause here and follow the Old Laptop Revival Guide's wipe and install-day chapters first. If it is a Raspberry Pi, the Raspberry Pi First Project Guide's SD-card and first-boot chapters do the same job. This chapter begins the moment your device boots to a desktop with working wifi, on any friendly Linux (or the Pi's flavor of it).

## 1. Update before anything else

Open a terminal (this is the last scary-looking moment; the rest is menus) and ask for the current state of the world:

```bash
sudo apt update && sudo apt full-upgrade -y
```

On some systems it is `sudo dnf upgrade -y` or similar; the device's own docs name the flavor. What matters is the habit, not the incantation: **updates first, always.** A home server's most common real-world wound is an old bug with a patch that arrived months ago and was never asked for.

When it finishes, run the same sentence the first Monday of every month. Write it on the [starter checklist](10-starter-checklist.md) — chapter 8 turns it into a whole ritual later, but tonight it is one command.

## 2. Give the machine a name

Your family's phones are about to meet this machine regularly, and "192.168.1.42" is a password built out of a sudoku. Servers answer better to names: open the system's settings (usually called *About* or *Hostname*), and name it something a family member could type from memory — `family-server` is popular for good reason. Lowercase, no spaces, short.

From now on, in every later chapter, the server is referred to by that name. When everything works, you can test it from your normal computer:

```bash
ping family-server
```

If the name resolves — replies come back — your router and the machine are cooperating. If it does not, an address like `family-server.local` usually does (most Linux editions answer on the network by that style of name automatically).

## 3. Pin the address down

DHCP — the glossary has the full story — hands out addresses at random, which means next Tuesday the server may be handed a new number, breaking every saved connection. The cure is a **DHCP reservation**: you tell the router "always give `family-server` the same number," and the router obeys forever.

1. From your normal computer, open the router's admin page (the sticker on the router names the address — often `192.168.1.1`).
2. Find the section usually called * DHCP / Address Reservation / Static Leases*, and reserve one address for the server's name.
3. Reboot the server; its address today becomes its address forever.

You have not opened anything to the internet here. A reservation is an interior decoration choice — the house's rooms get fixed numbers; the front door stays shut.

## 4. The sleep-cure (laptop owners, this is yours)

Old laptops love to nap. A server that naps is a server that misses family phones. The cure is two menu clicks in the power settings:

- **When the lid closes: do nothing.** (You will likely run it lid-closed in a corner — external-friendly, screen-off, fully awake.)
- **When idle: never sleep.** The machine is meant to sit, warm, humming quietly, indefinitely.

Mini PCs rarely sleep by default; check anyway. Raspberry Pi boards do not sleep at all, which is one of their honest charms.

## 5. Make tomorrow-you a note

Open any text editor and create one file, saved on *this* machine: `server-notes.txt`. Tonight's entries:

- the hostname (`family-server`)
- the reserved address (the number the router promised)
- which Linux flavor this is, roughly
- the update command

Every chapter adds a line to this note. In a year it will be the single most valuable file on the machine — the difference between "the server broke and I have no idea what is on it" and "the server broke and here is the recipe to rebuild it." (Chapter 8 makes a backup copy of the note itself, which sounds ridiculous until you need both copies at the same time. That day has visited all of us.)

## 6. The user account and one safety habit

If the Linux install created a personal user for you, that is your server login. Two habits worth setting tonight, both five minutes:

- **A password you do not use anywhere else.** The passwords-and-two-step guide explains why reuse is the quiet killer; this one password lives in your password manager like everything else.
- **Automatic security updates on**, if the system's software updater offers it. Automatic *everything*-updates is a personal choice, but security-only automation is free insurance while you sleep.

And a small courtesy: if the machine has a removable battery and lives plugged into the wall all year, leaving it at 80% charge (most systems have a "battery health" slider in power settings) gives the battery a decade instead of three years.

## What *not* to do tonight

The first-evening temptation list, in order of how common it is:

- **Installing the whole green-zone list in one sitting.** Chapter 5 says "one service per evening," and it means it.
- **Opening anything in the router's port-forwarding page.** "Port forwarding" is the phrase chapter 4 exists to talk you out of; nothing tonight needs it.
- **Naming the machine after its job in a way strangers could guess** (`photobackup-2026`). Inside names should be boring; secrecy here is not security, but clarity is kindness.
- **Skipping the update command to install "one thing" first.** No.

## Before you move on

- [ ] Updates ran, and the monthly date is on the starter checklist.
- [ ] The machine answers to its name (ping it once to be sure).
- [ ] The router now reserves its current address forever.
- [ ] The sleep-settings check is done, and it is set to never nap.
- [ ] `server-notes.txt` exists with tonight's four facts.
