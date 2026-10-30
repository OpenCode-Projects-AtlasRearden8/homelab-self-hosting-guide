# Chapter 4 — Remote Access Without Scary Exposure

Time: one evening, plus ten minutes per family member later. Tools: the server, your normal computer, one app per phone. Fear level: this chapter is designed to end some of it.

Here is the worry that stops most people from self-hosting: *if a machine is in my house holding my photos, and I can reach it from the coffee shop, can a stranger in a warehouse reach it too?* The answer, done the way this chapter teaches, is no — and the difference between yes and no is one idea, learned once, that protects everything else in this book.

## The front door problem

Your router is the only building between your home network and the internet, and it has two kinds of doors:

- **Outbound doors** (opening from the inside) — when your laptop visits a website. These open themselves, close themselves, and let nothing in behind them.
- **Inbound doors** (standing open from the outside) — the famous **port forwarding**, where you tell the router "let strangers from the internet knock on port 8080 and go straight to the family server."

That second kind is what most old tutorials tell you to configure. Do not — not tonight, not "just temporarily," not even "with a strong password." Here is the plain reason: **the internet's background noise is not theoretical.** Automated bots crawl the public internet all day, every day, knocking on *every* door of *every* address they can find, by machine, in their millions. They do not know or care what you host; they knock, they try default passwords, they try old bugs. A forwarded port on a home address is a door that gets knocked on within hours. Some of those knocks are polite. Some are not polite forever.

The safe pattern — used by small businesses and careful hobbyists alike — is to give yourself a **private lane** that runs *around* the public doors entirely. Strangers cannot knock on a lane they cannot see, and the lane exists only for people you invited.

## The private lane: a family VPN

A **VPN** (glossary has the plain-English version) here is not the "watch Netflix from another country" product. It is a private road only your devices can drive on, ending at a door inside your router, invisible from the outside. When your phone at the coffee shop joins it, the phone behaves — for our purposes — as if it were sitting on your couch at home. Every service in this book becomes reachable *as if you were in the living room*, because from the lane's point of view, you are.

There are two friendly ways to build it:

### Tailscale (the recommended first lane)

**Tailscale** is free for personal use (its free tier is genuinely free, not a trial), installs in minutes, and needs no router configuration at all — it builds the private lane over the internet by itself. The mental model is a private club list: every device you approve gets a membership card; nothing else can even find the door.

1. Create a free account (a sign-in from one of your existing email providers is fine).
2. Install the Tailscale app on the server:

```bash
curl -fsSL https://tailscale.com/install.sh | sh
sudo tailscale up
```

3. A link appears in the terminal; open it, sign in, and the server joins your private network. Confirm it from your normal computer:

```bash
tailscale status
```

4. Install the app on each phone and laptop the family uses, sign in, done. The photo library, the wiki, the files — all reachable by the names they have at home.

From now on, *every* address this book gives you can be reached from anywhere, by any family member, with nothing exposed to strangers. Your grandmother in another town, on her sofa's wifi, is on the same private lane.

### Plain WireGuard (the DIY cousin)

**WireGuard** is the underlying technology, standard in modern Linux, and building the lane by hand — keys, router config, the works — is a genuinely good project for a slow weekend. It is more work and more control. But it starts on the router's configuration page, which means it starts near the temptation of inbound doors, so beginners should treat Tailscale as the default and WireGuard as the proud someday-project. The honest rule: **the tool you will actually finish is the right one.**

## The two-minute security posture

With the lane in place, this book's entire security stance fits in three sentences:

1. **Green-zone services answer only inside the house or on the lane — never on the open internet.** If an app's setup asks "expose this publicly?", the answer is no.
2. **The lane's door is your family's sign-in; keep those accounts strong** (unique passwords, and turn on its two-step prompt if you use one provider for sign-in).
3. **Anything that cannot live with those rules goes to chapter 9's cloud list instead.** No guilt; that chapter is not a consolation prize, it is an equal resident.

Notice what disappeared: port forwarding, dynamic DNS, certificate anxiety, "is my router's firewall good?", the fear of the coffee shop. The lane replaces all of it with one app-shaped question — "whose devices are on the list?" — and the answer is the same as the answer to "who is family?"

## What family members actually experience

Worth knowing, because family adoption is half of this chapter's success: after a one-time app install and sign-in, members' phones either keep the lane on (it sips battery and stays out of the way) or flip it on when they want the photos. Nothing else about their phone changes. When they open the photo library at grandma's house, it just... works, silently routing down the private road. The first time you watch it happen from a gas-station parking lot, it feels like magic, and it stays that way.

Fifteen minutes for the whole family, once, and every chapter after this one is automatically remote-ready.

## The checklist that keeps the lane honest

Four habits, all ابout five minutes a season:

- [ ] **New device?** Install the lane's app before anything else touches the family data.
- [ ] **Someone leaves the club** — a phone is sold, a guest's tablet goes home? Remove their device from the members list (the app's admin page is one screen).
- [ ] **A service you added asks for a public door?** No. (You know this one by now; perfect.)
- [ ] **The quarterly five:** check the members list is still exactly the family, glance at the app's update, done.

## Before you move on

- [ ] The server joined the private lane, and `tailscale status` shows it.
- [ ] One phone in the house reached the server from *away from home*.
- [ ] The whole family's devices are on the member list — and nobody else is.
- [ ] Port forwarding remains the thing you have never done, and you can explain why in one sentence: *"the lane means strangers never see the door."*
