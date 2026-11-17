# Unmanaged VPS Hosting: What You Handle Yourself, Which Plan Size Is Enough, and What the Sticker Price Leaves Out (With RackNerd's KVM Lineup)

Unmanaged VPS hosting trades a management fee for your own labour, and the trade only pays off if you can already run a Linux box without help. Install a stack over SSH, wire up alerts, keep backups running, and you get a server with full root access for a fraction of what a managed plan costs. If any of those three sounds like a weekend project you keep postponing, buy managed and skip the arithmetic below.

What follows covers the four things people actually want to know before paying: what the provider does and what you do, how much server a normal project needs, what RackNerd's unmanaged KVM plans cost per year, and the costs and limits that never make it into the headline price.

> **Quick answer:** the 2 GB plan is the one most people should buy — 2 vCores, 2 GB RAM, 35 GB SSD, 5 TB monthly transfer on a 1 Gbps port, **$35.99 per year**. It runs a LEMP stack, a VPN, a few containers and most one-click apps with room left over. Take the 1 GB at **$21.99/year** only for a VPN and static sites, and go above 4 GB only when you can name the app that needs the RAM. 👉 [Check RackNerd's current unmanaged KVM VPS specials and pricing](https://bit.ly/RacKnerd)

## What RackNerd's unmanaged VPS plans actually cost

Every plan below is a KVM virtual machine with full root SSH access, a dedicated IPv4 address, a 1 Gbps port and instant setup after payment. RackNerd sells them as annual specials, which means you pay twelve months up front rather than monthly.

| Plan | vCPU / RAM | SSD | Monthly transfer | Annual price | Order |
| --- | --- | --- | --- | --- | --- |
| 1 GB KVM | 1 vCore / 1 GB | 20 GB | 3 TB | $21.99/yr | [ 1 GB KVM VPS](https://bit.ly/RacKnerd) |
| 2 GB KVM (most popular) | 2 vCores / 2 GB | 35 GB | 5 TB | $35.99/yr | [ 2 GB KVM VPS](https://bit.ly/RacKnerd) |
| 4 GB KVM | 3 vCores / 4 GB | 60 GB | 7 TB | $59.99/yr | [ 4 GB KVM VPS](https://bit.ly/RacKnerd) |
| 6 GB KVM | 6 vCores / 6 GB | 100 GB | 12 TB | $89.99/yr | [ 6 GB KVM VPS](https://bit.ly/RacKnerd) |
| 8 GB KVM | 7 vCores / 8 GB | 150 GB | 20 TB | $119.99/yr | [ 8 GB KVM VPS](https://bit.ly/RacKnerd) |

Promotional lineups rotate, so treat those figures as the current annual rates for the KVM specials rather than a permanent price list. The live specials page is the only place the number you will actually be charged is authoritative; check it at the moment you order, because a promotion ending changes the price, not the hardware.

The panel matters as much as the specs here. Every special ships with `ctrl`, RackNerd's own control panel, which handles reboots, OS reinstalls, an out-of-band HTML5 VNC console, a network firewall, root password resets, plan upgrades and a catalogue of one-click apps. Installable systems are CentOS, Rocky Linux, AlmaLinux, Fedora, Debian and Ubuntu, with custom ISO installs available through a support ticket. That is the standard unmanaged deal done properly: you get the keys and the recovery console, and nobody stands behind you while you work.

## Who does the work on an unmanaged VPS

The split is consistent across every provider that publishes it: the hardware, power, network and hypervisor are theirs, everything from the operating system upward is yours.

| Job | On an unmanaged VPS | On a managed VPS |
| --- | --- | --- |
| Hardware, power, network, hypervisor | Provider | Provider |
| OS choice and control panel | You, with full root | Provider's supported image |
| OS and panel updates | You | Provider |
| Security patches, firewall rules | You | Provider, within scope |
| Monitoring (CPU, disk, uptime) | You | Provider |
| Backups | You, unless you buy a backup service | Usually daily, included |
| Application security, user accounts, data | You | You |
| Hardware and network SLA | **99.9% typical** | **99.95%+ typical** |

Even on an unmanaged plan, the provider keeps responsibility for physical server security and for core network and virtualisation. What shifts to you is firewall configuration, malware response, operating system patching and backup security. Those are the four items that generate the 2 a.m. problems.

The SLA gap is real but narrower than the marketing suggests. The 99.9% versus 99.95%+ figures above come from hosting.com's published comparison of its own two products, so read them as an example of the usual split rather than an industry standard, and check the SLA attached to whichever plan you buy. A 99.9% hardware and network commitment still leaves roughly 43 minutes a month of allowed downtime, and none of that covers your broken nginx config.

Support scope is where cheap and mid-range providers genuinely differ. Contabo states plainly that it does not manage your server: its team covers infrastructure questions, publishes a knowledge base and API docs, and staffs support 365 days a year between 08:00 and 23:00 German time, while project-level configuration issues are yours to solve or to hand to a system administrator you hire. RackNerd's specials page says support is available 24/7 for platform help. Both positions are honest and both stop at the same line: if your PHP-FPM pool is misconfigured, you will be told the hardware is healthy.

## The real monthly cost of unmanaged VPS hosting

Liquid Web puts the trade in one sentence worth quoting: "Compare total operating cost, not just the monthly server price." The saved management fee is paid for with hours, and the hours have a price even when nobody invoices you for them.

Run the numbers honestly. A first server takes an evening to harden, then maybe two to three hours a month to patch, review alerts, verify backups ran and fix whatever drifted. At $40 an hour, a $35.99 annual plan is carrying roughly $100 a month of your own labour. That is still a good deal if you enjoy the work or already have the routine. It stops being a good deal the month you skip patching because you were busy.

The second trap is term pricing. Contabo currently shows its CLOUD VPS 8 at 8 vCPU, 24 GB RAM, 300 GB SSD or 150 GB NVMe, 600 Mbit/s port and unlimited traffic for €14.00 a month, discounted to **€11.20/month for the first 24 months**, and does not publish what month 25 costs. Every "from $X" headline deserves that question, and the answer is usually in a footnote or nowhere at all.

RackNerd's structure avoids half the problem by billing annually: one payment, no month-two surprise, and the renewal question becomes visible a year ahead instead of at the end of a teaser period. One long-term customer running a 1 GB plan since October 2024, bought on a promotion that is no longer offered, reports that it has renewed at the same price and the same specs each cycle. That is one person's experience, not a contractual promise, but it is the behaviour you want to verify before committing a production site.

## The limits that live in the footnotes

Transfer allowances are where budget plans quietly diverge, and the wording rarely appears next to the price.

OVHcloud advertises unmetered traffic on its VPS range, then adds a footnote: in the Asia-Pacific region (Mumbai, Singapore, Sydney) there is a monthly quota of **500 GB on VPS-1, 1 TB on VPS-2 and VPS-3, and 3 TB on VPS-4**, after which bandwidth is throttled to 10 Mbps. A number like that turns a video proxy or a backup target into a very slow experience, and you only find it by reading the asterisk.

On RackNerd's lineup the ceiling is explicit in the specs: 3 TB to 20 TB of monthly transfer depending on plan, all on a 1 Gbps port. Match that against your actual egress. Serving a few sites and a VPN will not come close. Mirroring object storage, running a seedbox or relaying media will, and the plan you need is set by the transfer figure rather than the RAM.

Backups deserve their own line. RackNerd's `ctrl` panel covers power, reinstalls, console access, firewall rules, password resets and upgrades. Backups are not part of that list, so budget for your own: object storage plus a scheduled `restic` or `borg` job costs a few dollars a month and is the difference between a bad afternoon and a lost project. 👉 [Review RackNerd's VPS specials and confirm what each plan includes](https://bit.ly/RacKnerd)

## Which plan size fits your project

The RAM you need is set by the heaviest thing you plan to run, not by ambition.

- **1 GB / $21.99 a year.** One reviewer's entire production setup on this tier — a WireGuard VPN for phones and laptops, two nginx sites with Let's Encrypt certificates, a reverse proxy tunnelling to a home server, plus nftables and fail2ban — sits at about 230 MB of RAM with a load average near zero. A personal VPN and a couple of static sites fit comfortably.
- **2 GB / $35.99 a year.** The sweet spot, and the plan RackNerd marks as most popular. Enough for a LEMP or LAMP stack, a WordPress site with traffic, a small Docker set, n8n, or Coolify, which is comfortable from 2 GB.
- **4 GB / $59.99 a year.** The entry point for local AI tooling. Ollama, AnythingLLM, LibreChat and Hermes Agent all want at least 4 GB, and so does a server running several production containers side by side.
- **8 GB / $119.99 a year.** OpenClaw needs a minimum of 8 GB, which makes this the smallest plan that runs it. Same for hosting multiple heavy apps at once.
- **6 GB / $89.99 a year.** An awkward middle. Buy it only if a specific workload lands between the two, otherwise jump from 4 to 8.

That 1 GB plan doing real work is the useful data point here. Most personal projects are memory-light and disk-light, and the common failure is buying 8 GB to run a blog, not running out of RAM on 2 GB.

## Unmanaged or managed: pick with these rules

Buy unmanaged when you can tick most of these:

- You can administer Linux from a shell, including users, services, firewalls and logs.
- You need a specific or experimental software stack that managed hosts will not support.
- You already have monitoring, patching and backup routines you trust.
- Someone can respond when the server breaks, including outside office hours.
- The machine is a lab, a test bed, a learning project or a low-stakes personal service.
- The base price genuinely drives the decision.

Pay for managed instead when any of these is true:

- A business site, online store, agency client site or SaaS production environment depends on it, and downtime costs revenue.
- Nobody on the team is the designated sysadmin.
- Your technical people should be building the product, not scheduling kernel updates.
- You want someone else monitoring, patching and troubleshooting as part of the fee.
- You would rather have a control panel and a support queue than root access and total freedom.

One caveat that experienced teams get wrong: being good at server administration is not a reason to do it on a revenue-generating production box. Liquid Web's own framing is that even technically strong teams often choose managed hosting for production workloads, because server upkeep is not the best use of their hours.

## Three things to confirm before you pay

**Datacenter location.** Latency is set by distance. Pick the region closest to your users, and if you are running a VPN, the one closest to you.

**Transfer and port speed.** RackNerd lists 3 TB to 20 TB monthly with a 1 Gbps port. Confirm the figure for your chosen plan against your real egress, and check whether any regional cap applies.

**Backups and recovery.** Decide before you deploy whether you are buying a backup service or building one, and test a restore in the first week. An untested backup is a rumour.

**Term and upgrades.** Annual billing means one payment up front. Upgrades are handled inside `ctrl`, and moving up a plan means a reboot, so schedule it rather than discovering it during a traffic spike.

If you can name the workload and the RAM it needs, buy that plan and nothing larger. If you cannot name it, the 2 GB at $35.99 a year covers nearly every first server, and the difference between it and the tier above is better spent on a backup bucket. 👉 [Compare RackNerd's unmanaged KVM VPS plans and get started](https://bit.ly/RacKnerd)
