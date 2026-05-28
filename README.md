# Everyday Studio — Website

A single-page marketing site for **Everyday Studio**, an independent studio building small, useful apps for daily life.

- **Brand:** Everyday Studio
- **Live site:** [everyday-studio.everydaystudio.workers.dev](https://everyday-studio.everydaystudio.workers.dev)
- **Custom domain (future):** `everydaystudio.com`
- **Tagline:** *Useful apps for daily life.*
- **Contact:** `hello@everydaystudio.com` (set up after domain purchase)
- **Hosting:** Cloudflare Workers (free, auto-deploys from `main`)

## What's inside

```
everyday-studio/
├── index.html        # The site (semantic, accessible, no JS framework)
├── styles.css        # Design system + responsive layout
├── _headers          # Cloudflare Pages: security & caching headers
├── _redirects        # Cloudflare Pages: URL redirects (future app store links)
├── .gitignore        # Git ignore rules
├── README.md         # This file
├── DEPLOY.md         # Step-by-step Cloudflare + GitHub deploy guide
└── MARKETING.md      # Launch & growth playbook
```

## Preview locally

Open `index.html` directly, or serve it:

```bash
python3 -m http.server 8080
# or
npx serve .
```

Then visit `http://localhost:8080`.

## Deploy

This project is set up for **Cloudflare Pages** (free, fast, auto-deploys from GitHub).

👉 **Full step-by-step guide:** see [`DEPLOY.md`](./DEPLOY.md).

Already deployed at: **https://everyday-studio.everydaystudio.workers.dev**

Every `git push` to `main` auto-deploys in ~30 seconds via Cloudflare Workers Builds.

Setup steps (already completed, kept for reference):
1. GitHub repo created at `Liljanameti/everyday-studio`.
2. Cloudflare account created, free plan.
3. Workers & Pages → Connect to Git → repo connected.
4. Workers subdomain set to `everydaystudio.workers.dev`.

## Buying the domain

Register `everydaystudio.com` once you're ready. In order of preference:

- **Cloudflare Registrar** — at-cost pricing (~$10/yr), no markup. Best because your domain, DNS, and hosting all live in one place.
- **Porkbun** — clean UX, fair prices, free WHOIS privacy.
- **Namecheap** — beginner-friendly.

Avoid GoDaddy (constant upsells, expensive renewals).

## Customize

| Want to change... | Edit |
|---|---|
| Brand name | `index.html` — search "Everyday Studio" |
| Tagline | `index.html` — `<h1>` in `.hero-copy` |
| Featured app | `index.html` — `.app-feature` section |
| "More in the works" hints | `index.html` — `.hint-list` items |
| Colors | `styles.css` — `:root` variables at the top |
| Fonts | `index.html` Google Fonts + `styles.css` `--font-*` |
| Contact email | `index.html` — `mailto:hello@everydaystudio.com` |

### Quick color swap
```css
--accent: #f59e0b;       /* primary (warm amber) */
--accent-deep: #d97706;
--accent-soft: #fef3c7;
```

## Suggested next steps

1. Register `everydaystudio.com` (Cloudflare or Porkbun, ~$10/yr).
2. Set up `hello@everydaystudio.com` (Fastmail $5/mo or Zoho free).
3. Deploy the site (Netlify drag-and-drop).
4. Hook up the newsletter form (see `MARKETING.md`).
5. Add favicons & social preview images.
6. Read `MARKETING.md` and execute the 90-day launch plan.
