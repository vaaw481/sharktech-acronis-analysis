# data backup software: what Sharktech's $4/month Acronis plan actually covers, which billing cycle costs less in the long run, and who should skip it

Most people searching for data backup software want the same three answers: what it costs for a realistic amount of storage, whether the "ransomware protection" claim holds up, and which plan they should actually pick. Here's the short version. Sharktech resells the full Acronis Cyber Protect platform — the same product PCMag rated 4.5/5 with an Editors' Choice — on a per-storage pricing model that starts at **$4/month for 200GB**. That's an unusually low entry point for managed Acronis, and the trade-offs are mostly buried in the overage rates, which we'll do the math on below.

Sharktech itself isn't a backup vendor by origin. It's a hosting company founded in 2003 that runs data centers in Los Angeles, Chicago, Denver, and Amsterdam, and it added Acronis Backup Service as an official product in early 2026. That background matters for one practical reason: if your servers already live on Sharktech, backups travel over the same provider's network with no egress fees between your box and the backup target.

> **Quick picks**
> - Most small setups (1–10 machines, under ~200GB): the monthly Acronis plan at $4/month, 200GB included. Flexible, lowest overage rate, no long commitment. [👉 see the monthly plan with 200GB included](https://portal.sharktech.net/cart.php?a=add&pid=648&configoption%5B1862%5D=200&configoption%5B1863%5D=0&billingcycle=monthly&aff=1626)
> - Stable, known-size workload: annual at $24/year (~$2/month), but only if you're sure you won't blow past 200GB.
> - Already running Borg, Restic, or Veeam on your own: the S3 Object Storage plan at $4.90/TB/month instead.
> - Needing PB-scale, multi-region retention: this isn't your product; that's AWS/Azure territory.

## What "data backup software" actually means when you're shopping

The term covers two very different product categories, and mixing them up is how people end up overpaying.

The first category is consumer and small-business backup software — the Acronis True Image, EaseUS ToDo Backup, and AOMEI Backupper style of tools that dominate "best of" lists from TechRadar and PCWorld. These run on your machine, image your disk or sync selected folders, and usually charge per device or per year.

The second category is what Sharktech sells: the business-oriented Acronis Cyber Protect platform, hosted by a provider. You install an agent on each machine, backups run to the provider's cloud storage on a schedule you set, and you manage everything through a central web console. Pricing here is normally quoted per workload with a storage line item — which is exactly where Sharktech's model differs, and where the real decision lives.

## Sharktech Acronis Cyber Protect: all plans and current pricing

Every Acronis plan includes **200GB of cloud storage**, and anything beyond that is billed per GB at a rate that depends on your billing cycle. There's also a separate S3 Object Storage plan for people who bring their own backup tool. The full list as currently sold:

| Plan | Included storage | Price | Overage rate | Buy |
| --- | --- | --- | --- | --- |
| Acronis Cyber Protect – Monthly | 200GB | $4.00/mo | $0.02/GB | [ Order monthly](https://portal.sharktech.net/cart.php?a=add&pid=648&configoption%5B1862%5D=200&configoption%5B1863%5D=0&billingcycle=monthly&aff=1626) |
| Acronis Cyber Protect – Quarterly | 200GB | $8.00 / 3 mo | $0.04/GB | [ Order quarterly](https://portal.sharktech.net/cart.php?a=add&pid=648&configoption%5B1862%5D=200&configoption%5B1863%5D=0&billingcycle=quarterly&aff=1626) |
| Acronis Cyber Protect – Semi-Annual | 200GB | $12.00 / 6 mo | $0.06/GB | [ Order semi-annually](https://portal.sharktech.net/cart.php?a=add&pid=648&configoption%5B1862%5D=200&configoption%5B1863%5D=0&billingcycle=semiannually&aff=1626) |
| Acronis Cyber Protect – Annual | 200GB | $24.00 / yr | $0.12/GB | [ Order annually](https://portal.sharktech.net/cart.php?a=add&pid=648&configoption%5B1862%5D=200&configoption%5B1863%5D=0&billingcycle=annually&aff=1626) |
| S3 Object Storage | 1TB (scalable) | $4.90/TB/mo | 1TB bandwidth included, then metered | [ Order S3 storage](https://portal.sharktech.net/cart.php?a=add&pid=643&carttpl=s3_storage_cart&billingcycle=monthly&configoption%5B1858%5D=13673&configoption%5B1859%5D=1&aff=1626) |

A couple of things the table can't show. File Sync & Share is an optional add-on across the Acronis plans ($0.03/GB/month on the monthly cycle, up to $0.24/GB/year on annual); most solo operators and small teams don't need it, so leave it unchecked unless you specifically want Dropbox-style syncing bolted onto your backup. And your final configured price depends on the capacity and protection options you select in the cart, so check the itemized total before confirming.

## The billing cycle trap: longer terms cost more per extra GB

This is the part almost nobody explains, and it flips the usual "prepay for a year and save" logic on its head.

The base price does follow the normal pattern — annual works out to roughly $2/month versus $4/month for monthly billing. But the **overage rate runs the other way**. Monthly billing charges $0.02 per GB beyond your 200GB; annual billing charges $0.12 per GB, six times as much. Concretely: every extra terabyte costs about $20.50/month on the monthly plan versus about $123/month on the annual plan.

So the decision rule is straightforward:

- **Data will likely grow past 200GB** → monthly, always. The $4 base is only $2/month more than annual, and a single extra 100GB costs you $2/month instead of $12.
- **Data is a known, stable quantity under 200GB** → annual at $24/year is genuinely cheaper, and there's no overage to worry about.
- **Quarterly and semi-annual** exist for people who want a small discount on the base without a full-year commitment. They're middle-of-the-road on everything, including overage ($0.04 and $0.06/GB), and honestly the case for picking them over monthly is thin unless you just dislike monthly billing.

[👉 Configure the monthly plan and see your live total in the cart](https://portal.sharktech.net/cart.php?a=add&pid=648&configoption%5B1862%5D=200&configoption%5B1863%5D=0&billingcycle=monthly&aff=1626) before committing to a cycle — the cart shows the exact figure for your chosen capacity.

## What Acronis Cyber Protect actually does

The reason to pick hosted Acronis over a cheap plain-backup service is the platform itself, and this isn't a stripped-down reseller version — it's the same Cyber Protect engine Acronis sells directly, running on Sharktech's infrastructure.

On the backup side, one agent and one web console cover physical machines, VMs, and cloud workloads across 30-plus platform types: Windows (7+), Windows Server (2008 R2+), Linux, macOS (10.9+), VMware vSphere, Hyper-V, KVM, Proxmox, Nutanix AHV, Virtuozzo, plus application-level backups for Microsoft SQL, Exchange, and SharePoint. Mobile devices are covered too (Android 4.1+, iOS 8+). Recovery granularity goes from a single file, to folders, to a full bare-metal restore — including restoring to different hardware, the "universal restore" feature that shows up repeatedly in TrustRadius user reviews as a highlight.

On the security side, the Active Protection module does AI-based anti-ransomware monitoring — watching process behavior and intercepting encryption attempts in real time — and it's included in Cyber Protect Cloud rather than billed as a separate EDR subscription. The anti-malware engine has been validated by AV-Test, AV-Comparatives, and ICSA Labs, and PCMag's 4.5/5 Editors' Choice review of Acronis Cyber Protect 17 specifically credited the integrated backup-plus-security approach and GDPR/HIPAA compliance support. Acronis also picked up Leader placements in four separate G2 categories in the Summer 2026 Grid Reports (including #2 in SaaS Backup and #3 in Cloud Security).

One detail worth knowing before you buy: the product page notes that application and database protection depends on workload support and licensing, and that features like File Sync & Share and certain disaster-recovery options may be priced separately. Retention periods are configurable per protection plan, and recovery points are kept for as long as your policy defines — longer retention means more stored data, which means more overage on a 200GB plan.

## How it stacks up against the obvious alternatives

The comparison most buyers end up making is against Liquid Web's hosted Acronis, since both target the same managed-hosting audience. Liquid Web's Acronis Cyber Backups start at $11/month for 100GB **plus a base workload fee**, climbing to $134/month at 1TB. Sharktech's equivalent entry is $4/month for 200GB — roughly a third of the entry price for double the base storage, with no workload fee on top. Liquid Web bundles more hand-holding; Sharktech is the self-serve option.

| Option | Pricing model | Entry price | Notes |
| --- | --- | --- | --- |
| Sharktech Acronis Cyber Protect | Per GB stored | $4/mo, 200GB included | Ransomware protection included; no workload fee |
| Liquid Web Acronis Cyber Backups | Per workload + storage | $11/mo, 100GB + base fee | More managed support bundled in |
| Acronis direct | Per device/workload license | ~$85/yr/device, storage not included | You arrange your own storage target |
| Backblaze B2 (object storage) | Per TB stored | ~$6.95/TB/mo | DIY only; pairs with your own backup tool |

Each of those makes sense somewhere. If compliance requires a deeply managed provider relationship, Liquid Web's bundle may justify its price. If you'd rather buy Acronis licenses directly, you can — but you'll handle storage separately. The Sharktech plan wins mainly on the shape of the bill: one predictable per-GB number, which is also why MSPs use it for client quoting.

## The second path: S3 Object Storage at $4.90/TB for people who already have a tool

If you already run Borg, Restic, Duplicacy, Veeam, rclone, or anything S3-compatible, you don't need Acronis at all — you need a storage target. Sharktech's S3 Object Storage plan is a flat **$4.90/TB/month** with 1TB of bandwidth included and no per-request API fees. That undercuts Backblaze B2's ~$6.95/TB, and unlike most rock-bottom object storage offers, there's no long-term contract or capacity commitment behind the rate. Storage clusters span Sharktech's data centers, and because it speaks standard S3, it plugs into Jenkins, GitLab, Terraform, and MinIO clients without custom integration. [👉 Set up the S3 Object Storage plan here](https://portal.sharktech.net/cart.php?a=add&pid=643&carttpl=s3_storage_cart&billingcycle=monthly&configoption%5B1858%5D=13673&configoption%5B1859%5D=1&aff=1626) if that describes you.

One less-obvious benefit of keeping backups with your hosting provider: no egress fees between your servers and the backup target. Moving a terabyte of backup data to a third-party cloud is where surprise bandwidth bills usually come from.

## Who shouldn't buy this

Being upfront about the limits, because three groups should look elsewhere.

If you're backing up a handful of personal laptops and just want a local external-drive-style copy, a one-time-license consumer tool is cheaper over a few years. If you need petabyte scale with custom retention policies across multiple regions, Sharktech's package is built for the small-to-mid market, and you should be talking to a hyperscaler or an enterprise backup vendor instead.

And there's a policy caveat worth checking before checkout: third-party summaries of Sharktech's terms note the company does not advertise a money-back guarantee, and its Trustpilot score sits around 3.5 on a modest number of reviews — typical for an infrastructure provider, with praise for network latency and support responsiveness, but it means the monthly plan is effectively your trial. Starting month-to-month is the sensible way to validate the service before any longer commitment.

## Getting started: five steps that avoid the usual mistakes

1. **Pick the billing cycle by growth, not by discount.** Monthly if your data might grow; annual only for a known, stable quantity under 200GB.
2. **Start with the 200GB base and let overage absorb growth.** You won't have to manually migrate to a bigger tier.
3. **Skip File Sync & Share** unless your team specifically needs file syncing — it's the add-on most likely to silently pad the bill.
4. **Deploy the agent and set schedules once.** The console handles retention and recovery points from there.
5. **Test a restore in week one, not during an emergency.** Recovering a single test file proves the whole pipeline works while it's still free of stakes.

On that last point: Sharktech's own product page makes the same argument — recovery starts before the incident, and testing restoration should be part of your operating routine, not an afterthought.

## FAQ

**Does it back up Microsoft 365 or email data?** The Acronis platform supports Microsoft 365 data backup along with application-level backups for SQL, Exchange, and SharePoint; whether your specific workload is covered depends on the licensing and options you select at checkout, so confirm it in the cart configuration.

**Is there a free trial?** Sharktech doesn't advertise one for this service. The practical equivalent is the $4/month plan — one month's commitment is the cheapest way to find out if it fits.

**Will backups eat my bandwidth bill?** Not between Sharktech servers and Sharktech backup storage; there's no egress fee on that path. The S3 plan includes 1TB of bandwidth per month, with usage metered beyond that.

**Can I restore to different hardware after a failure?** Yes. Universal restore lets you recover a full machine image onto dissimilar hardware without reinstalling the OS first — the feature users most consistently single out in reviews of the platform.

## The bottom line, per situation

Running one or two servers under ~200GB and have been putting off backups because quotes kept landing at $50+ a month: the monthly plan at $4 is the one that finally makes "just do it" the cheap option. Data size is locked in and small: annual at $24/year is the better deal, with the caveat that its overage rate punishes growth. Already married to Restic or Veeam: skip Acronis and take the $4.90/TB S3 target instead. And if you'd rather have a vendor-run managed Acronis with more hand-holding regardless of price, Liquid Web plays that role — just know it starts at $11/month for half the storage. [👉 Start with the annual plan at $24/year if your data is stable](https://portal.sharktech.net/cart.php?a=add&pid=648&configoption%5B1862%5D=200&configoption%5B1863%5D=0&billingcycle=annually&aff=1626), or fall back to monthly if it isn't — and test a restore in your first week either way.
