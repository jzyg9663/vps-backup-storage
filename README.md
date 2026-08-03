# VPS for Backup: Up to 8TB Storage from $3.99/mo, the Offsite Backup Setup You've Been Sleeping On

Your laptop crashes. Your dev server gets wiped by a stray `rm -rf`. Your cloud provider has an outage that lasts two days. These aren't hypotheticals—they happen, and they happen to careful people who thought they had it handled.

The funny thing is, most people don't actually need a sophisticated backup strategy. They need an *offsite* backup that isn't on the same machine, ideally in a different city, running something stupid-simple like rsync or Restic. And for that? A VPS for backup is one of the cleanest solutions on the table—and one of the most underrated.

Let's talk about how to actually set one up, and why DediRock's Storage VPS lineup is genuinely interesting for this use case.

---

**Why a VPS for Backup Makes More Sense Than You'd Think**

The instinct when you need backup storage is to reach for a cloud object storage service—Backblaze B2, Wasabi, AWS S3. And hey, those are fine. But there's a case to be made for using a plain VPS for backup instead:

- **Full control.** You pick the OS, the tools, the access method. Want to run Restic's `rest-server`? A Samba share? rsync over SSH? All of it works on a VPS, no proprietary API required.
- **Flat pricing.** Object storage bills can surprise you—egress fees, API call costs, per-request charges. A VPS gives you a flat monthly bill. You know exactly what it costs.
- **Versatility.** The same VPS you use for offsite backups can moonlight as a Nextcloud instance, a Wireguard relay, or a lightweight monitoring box. It's not a single-purpose appliance.
- **Price-to-GB ratio.** This is where things get interesting.

A user on LowEndTalk ran the numbers when comparing options for 2TB of backup space. Backblaze B2 would have cost $144/year. iDrive E2 was $99/year after the first-year promo. DediRock's Storage Plus plan (with a promotional annual rate) came out to around $28.68/year. That's not a typo. The same 2TB, at roughly one-fifth the ongoing cost, with no API fees.

---

**The 3-2-1 Rule and Where a VPS Fits**

If you're not familiar with the 3-2-1 backup strategy, here's the short version: keep **3** total copies of your data, on **2** different types of media, with **1** copy stored offsite. It's the standard recommendation from sysadmins and security folks alike, and for good reason—it protects against hardware failure, ransomware, and physical disasters all at once.

A VPS for backup is a clean, affordable way to check that "1 offsite" box. Your local machine has copy #1. An external drive or NAS has copy #2. Your remote VPS is copy #3, sitting in a datacenter on the other side of the country (or world), completely isolated from whatever's happening at home.

The beauty of this setup is that it's automated-friendly. Tools like Restic, Borg, or even plain rsync can run scheduled jobs that ship your encrypted backups to the VPS without you doing anything after the initial configuration. Set it up once, and it just runs.

👉 [Start your VPS backup setup with DediRock](https://bit.ly/DediRock)

---

**DediRock Storage VPS: What You Actually Get**

DediRock is a US-based hosting provider—they have datacenters in Los Angeles and New York—and they've built a reputation in the low-end hosting community for punching well above their price point. Their Storage VPS line is specifically built for exactly this kind of use case: remote backups, archives, Nextcloud instances, long-term file storage.

Here's the full current lineup:

| Plan | Storage | RAM | Bandwidth | Price |
| --- | --- | --- | --- | --- |
| **Storage Starter** | 256 GB | 512 MB | 1 TB | $3.99/mo |
| **Storage Essentials** | 1 TB | 1 GB | 2 TB | $5.99/mo |
| **Storage Plus** | 2 TB | 2 GB | 4 TB | $9.99/mo |
| **Storage Advanced** | 4 TB | 4 GB | 8 TB | $18.99/mo |
| **Storage Premium** | 8 TB | 8 GB | 16 TB | $35.99/mo |

All plans run KVM virtualization, come with 1 dedicated IPv4, and connect at 1 Gbps. The host nodes run on Intel Xeon hardware with large SATA arrays—these are purpose-built storage boxes, not repurposed compute nodes.

First-month promotional pricing brings the Starter down to **$1.99** and Essentials to **$2.99**, which is basically the cost of a cup of coffee to get your offsite backup situation sorted.

👉 [Check current Storage VPS pricing and promos](https://bit.ly/DediRock)

---

**Choosing the Right Plan for Your Backup Needs**

The sizing question is actually pretty easy once you think about how much data you're backing up (and whether you're keeping multiple versions).

**If you're backing up a personal machine or a small blog:** The Storage Starter at 256 GB is more than enough for most people. Your photos, documents, and config files probably don't exceed 100 GB of actual data—with incremental backups and some compression, this plan covers you comfortably.

**If you're a developer or small team:** The Storage Essentials plan at 1 TB is the sweet spot. You can run a full Restic repo with 30-day retention, back up a few servers, and still have headroom. This is the one most homelab folks gravitate toward.

**If you're running multiple VMs or need a Nextcloud setup:** Storage Plus at 2 TB starts making sense. One LowEndTalk user ran Restic backups from South Korea to their DediRock Plus plan and reported 12 MB/s upload throughput without issues—plenty for routine backup jobs.

**If you're running a business with significant data:** Storage Advanced (4 TB) or Storage Premium (8 TB) covers serious workloads—multiple servers, database dumps, media archives, the works.

👉 [Browse all DediRock Storage VPS plans](https://bit.ly/DediRock)

---

**What Real Users Are Saying**

Community reviews from LowEndTalk and Trustpilot paint a consistent picture. Here's the kind of feedback that comes up repeatedly:

One user running Restic via Docker (plus Filebrowser for casual access) called the price-to-GB ratio "unreal"—especially compared to managed object storage services. Their main caveat was that a single vCPU can be a mild bottleneck if you're doing heavy encryption (like Tailscale tunnels at full speed), but for standard rsync or Restic jobs, it's a non-issue.

Another user on LowEndTalk noted: *"Their VPS performance is stable, network quality is reliable, and I haven't had to deal with unexpected downtime or strange issues that you sometimes see with other providers. When I've had questions or needed help, the responses were fast and actually useful—not copy-paste replies."*

The Trustpilot rating reflects similar sentiments—people consistently mention the value and the occasional solid promotional deal as the main draws.

---

**Current Promotions Worth Knowing About**

DediRock runs promotional deals fairly regularly, and a few are worth flagging:

- **Dedicated Server Discount:** Use promo code `15OFFDEDI` for **15% off for life** on all dedicated server plans.
- **First Month Discounts:** Storage Starter drops to $1.99 first month, Essentials to $2.99, Plus to $4.99—these come and go, so it's worth checking what's active.
- **Annual Storage Promo Plans:** DediRock has run annual pricing on Storage plans starting at around $11.88/year through special promotions—watch their announcements page for these.

For the most current active deals (they do update), the billing portal is the source of truth.

👉 [See active DediRock deals and promotions](https://bit.ly/DediRock)

---

**Setting Up Your VPS for Backup: The Short Version**

Once you've got your DediRock Storage VPS spun up, here's the basic flow that most people follow:

1. **Install your backup tool.** Restic and Borg are both excellent choices. Restic is arguably easier to get started with. On the VPS side, you can run `rest-server` (for Restic) or just use plain SSH/rsync.
2. **Initialize your repo.** `restic init` or equivalent creates an encrypted repository on the remote server.
3. **Run your first backup.** Point it at the directories you care about—documents, databases, config files, whatever.
4. **Set up a cron job.** On Linux, a simple cron entry running `restic backup` nightly handles everything automatically. On Windows, Task Scheduler does the same job.
5. **Test a restore.** This part people skip, and it's the most important step. A backup you've never restored is a backup you don't actually trust.

The whole setup from signing up to first successful backup run takes maybe 30-45 minutes if you've never done it before, less if you have. It's not glamorous, but it's the kind of thing you set up once and completely forget about—until the day you need it, and then you're extremely glad you did.

---

**The Bottom Line**

Using a VPS for backup isn't a compromise—for most individuals, developers, and small businesses, it's actually the smarter choice compared to managed object storage. You get full control, predictable pricing, and the flexibility to use any backup tool you want.

DediRock's Storage VPS lineup makes this especially compelling. Starting at $3.99/month for 256 GB (or $1.99 for the first month), scaling up to 8 TB for teams with serious storage needs, and running on purpose-built storage hardware in US datacenters—it checks the right boxes without asking you to pay cloud-provider prices.

If you've been putting off getting your offsite backup sorted, this is a pretty low-stakes way to stop procrastinating.

👉 [Get your VPS for backup sorted with DediRock](https://bit.ly/DediRock)
