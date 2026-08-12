# Clinairo Outreach Landing Pages

Three standalone single-page sites for cold outreach domains. Each folder deploys
independently — set the folder as the Vercel project root.

```
getclinairo.com/    Angle A — Consult Recovery (the wedge)
useclinairo.com/    Angle B — The Revenue Leak Map (funnel economics)
clinairohq.com/     Angle C — AI Front Desk (broadest entry point)
```

## Why the three are different

These are not three copies. Each leads with a different message so your cold email
sequences can test which one actually converts:

| Domain | Hook | Best for |
|---|---|---|
| getclinairo.com | "She said she'd think about it. Then what?" | Practices running ads that know they lose consults |
| useclinairo.com | "You already paid for the patients you're losing" | Owners who think in cost-per-lead terms |
| clinairohq.com | "Your front desk went home at five. Your patients didn't." | Colder audiences, broadest entry point |

Match the landing page to the email angle. Don't send the same email to all three.

## Deliberately noindex

Every page carries `<meta name="robots" content="noindex, nofollow">` and a `robots.txt`
that disallows everything. This is intentional:

- Three similar sites all linking to clinairo.com is a pattern Google's link-spam
  guidelines describe. Noindexing removes the risk entirely.
- Outreach domains competing with your main site in search helps nobody.
- The canonical tag on each points at `https://www.clinairo.com/`, so any authority
  consolidates on the real site.

These pages exist to look legitimate when a prospect Googles the domain in your email
signature, and to convert the ones who click. Not to rank.

## Tracking

All three carry the same GA4 property (`G-F86MY7M3YV`) with a `landing_domain`
parameter on every event, so you can compare domains in one report.

Events: `calculator_used`, `book_call_click` (with a `from` parameter for hero /
calculator / fallback), `main_site_click`, `email_click`.

In GA4, add `landing_domain` as a custom dimension (Admin → Custom definitions) to
break conversions down by domain.

## Deploying each one

1. New Vercel project, point it at the domain's folder
2. Framework Preset: Other
3. Add the domain under Settings → Domains
4. No build step

## Before you send a single email

**Warm the domains first.** They were registered recently, and cold email from domains
under ~30 days old lands in spam regardless of what the landing page looks like. Set up
SPF, DKIM and DMARC on each, then run them through a warming tool for two to three weeks
before real sending volume.

The landing pages are not the bottleneck on reply rate. Domain reputation is.
