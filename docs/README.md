# SuitUp landing page

Static site (no build step): `index.html` + `privacy.html` + `style.css`.
Palette mirrors `app/lib/theme.dart` (coffee/espresso/caramel/cream).

Purpose: the public web presence affiliate networks (Sovrn, AWIN, Rakuten,
Skimlinks) check during publisher review, plus the privacy-policy URL Google
Play requires. Includes the affiliate disclosure both networks want to see.

## Deploy to GitHub Pages (automated)

Publishing is automatic: the `website-publish` GitHub Action
(.github/workflows/website-publish.yml) copies this folder to
`suitup-catalogs/docs/` on every push to `main` that touches `website/`
(same `CATALOGS_PUSH_TOKEN` secret as the catalog refresh). You can also
trigger it manually from the Actions tab.

One-time setup after the first run: suitup-catalogs repo → Settings → Pages →
Source: Deploy from a branch → Branch `main`, folder `/docs` → Save. Site
appears at `https://amittal2001.github.io/suitup-catalogs/` within a minute;
later edits go live on push with no manual steps.

## Custom domain (recommended before affiliate applications)

Networks treat free `github.io` subdomains as a weak signal. Buy a domain
(e.g. `suitup.app`, `getsuitup.com` — ~$10/yr, avoid brand names like "zara"
in it):

1. Registrar DNS: add a CNAME record pointing `www` →
   `amittal2001.github.io`, and A records for the apex per GitHub's docs.
2. suitup-catalogs → Settings → Pages → Custom domain → enter the domain →
   enforce HTTPS.
3. Update the contact email on the site to one at the domain if you set up
   email forwarding (improves ownership verification with networks).

## Before applying to networks

- Replace the `mailto:` placeholders if you get a domain email.
- Keep business name / email / description IDENTICAL across this site, the
  Play Store listing, and every network application.
