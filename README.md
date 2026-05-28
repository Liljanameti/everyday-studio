# Everyday Studio — Website

A single-page marketing site for **Everyday Studio**, an independent studio building small, useful apps for daily life.

- **Brand:** Everyday Studio
- **Domain:** `everydaystudio.com`
- **Tagline:** *Useful apps for daily life.*
- **Contact:** `hello@everydaystudio.com`

## What's inside

```
everyday-studio/
├── index.html        # The site (semantic, accessible, no JS framework)
├── styles.css        # Design system + responsive layout
├── README.md         # This file
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

## Deploy (free, under 5 min)

### Option A — Netlify (drag & drop)
1. Go to https://app.netlify.com/drop
2. Drag the `everyday-studio` folder in.
3. Free `*.netlify.app` URL instantly.

### Option B — Vercel
```bash
npm i -g vercel
cd everyday-studio
vercel
```

### Option C — GitHub Pages
1. Push this folder to a new GitHub repo.
2. Settings → Pages → Source: `main` / root.

### Connect `everydaystudio.com`
Once deployed, your host (Netlify/Vercel) will give you DNS records to set at your registrar. Both have one-click guides under "Custom domain".

## Buying the domain

Register `everydaystudio.com` at one of:

- **Cloudflare Registrar** — at-cost pricing (~$10/yr), best for tech-savvy.
- **Porkbun** — clean UX, fair prices, free WHOIS privacy.
- **Namecheap** — beginner-friendly, lots of guides.

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
