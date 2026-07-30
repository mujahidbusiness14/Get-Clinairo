# getclinairo.com — Outreach Landing Page

**Angle:** Missed Call Recovery
**Headline:** "Stop Losing Patients to Voicemail"

This is a single-page landing site for outreach/ad campaigns pointing at
getclinairo.com. It shares Clinairo's design system and the exact same ROI
calculator logic as the main site (clinairo.com), with unique hero copy
for this specific angle.

## What's in this folder

- `index.html` — the entire landing page (self-contained, no build step)
- Favicon set + `site.webmanifest`
- `robots.txt` + `sitemap.xml` (pre-configured for getclinairo.com)

## Deploy to Vercel

1. Push this folder to its own GitHub repo (e.g. `getclinairo-landing`)
2. In Vercel: Add New → Project → import that repo
3. Framework Preset: **Other** (no build step needed — it's static)
4. Deploy
5. In the Vercel project: Settings → Domains → add `getclinairo.com` and
   `www.getclinairo.com`, then update your domain's DNS per Vercel's instructions

## What's already wired in

- **ROI calculator** — identical formulas to the main site's homepage
  calculator
- **Anonymous lead logging** — every calculator submission is saved to the
  same Firestore project as the main site (`audit_submissions` collection),
  tagged with `source: "getclinairo"` so you can see in Firestore which domain
  is actually generating the most engaged visitors
- **All CTAs** point to `https://www.clinairo.com/contact.html` — leads
  always land in the same place regardless of which domain sent them

## Before this works live

The Firestore security rules need to be updated once (if not already done)
to accept the optional `source` field this page sends. The updated rules
are in the main project's `firebase/firestore.rules` file — paste that
into Firebase Console → Firestore Database → Rules → Publish. This is
backward-compatible and won't affect the main site's existing forms.
