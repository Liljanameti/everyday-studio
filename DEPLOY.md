# Deploy to Cloudflare Pages (free, via GitHub)

This is your one-time setup. After this, every `git push` automatically rebuilds and redeploys the site.

**Time required:** about 10 minutes total.

---

## Step 1 — Create a GitHub repo (2 min)

1. Go to https://github.com/new (sign in if needed).
2. Repository name: **`everyday-studio`**
3. Description: *"Everyday Studio — useful apps for daily life."*
4. Visibility: **Public** is fine (and gets you free GitHub Pages as a backup). Choose **Private** if you'd rather keep it hidden — Cloudflare Pages works either way.
5. **Do NOT** check "Add a README", "Add .gitignore", or "Add license" — you already have these locally.
6. Click **Create repository**.

GitHub will now show you a page with instructions. Ignore them and use the commands below.

---

## Step 2 — Push your local code to GitHub (1 min)

In this terminal, run these (replace `YOUR-USERNAME` with your GitHub username):

```bash
cd ~/repos/everyday-studio

# Optional but recommended: use a personal identity for this repo only
git config user.name  "Your Name"
git config user.email "your-personal-email@example.com"

# Connect the local repo to GitHub
git remote add origin https://github.com/YOUR-USERNAME/everyday-studio.git
git push -u origin main
```

GitHub will ask you to authenticate. Two options:

- **Easy:** Use a [Personal Access Token](https://github.com/settings/tokens?type=beta) — create one with `repo` scope, paste it as the password when prompted.
- **Better long-term:** Set up SSH keys (https://docs.github.com/en/authentication/connecting-to-github-with-ssh) and change the remote to `git@github.com:YOUR-USERNAME/everyday-studio.git`.

After this completes, refresh your GitHub repo page — you'll see your files there.

---

## Step 3 — Create a free Cloudflare account (2 min)

1. Go to https://dash.cloudflare.com/sign-up
2. Enter your email + a strong password.
3. Verify your email.

That's it. No credit card needed. Cloudflare Pages is genuinely free with **500 builds/month** and **unlimited bandwidth** — far more than you need.

---

## Step 4 — Connect Cloudflare Pages to your GitHub repo (3 min)

1. In the Cloudflare dashboard, in the left sidebar click **Workers & Pages** (or visit https://dash.cloudflare.com/?to=/:account/pages).
2. Click **Create application** → **Pages** tab → **Connect to Git**.
3. Click **Connect GitHub**.
4. Authorize Cloudflare — you can grant access to **all repos** or **only `everyday-studio`** (recommended: only `everyday-studio`).
5. Back in Cloudflare, pick the **`everyday-studio`** repo and click **Begin setup**.
6. Configure the build:
   - **Project name:** `everyday-studio` (this becomes part of your URL)
   - **Production branch:** `main`
   - **Framework preset:** **None**
   - **Build command:** *leave empty*
   - **Build output directory:** *leave empty* (or `/`)
   - **Environment variables:** none needed
7. Click **Save and Deploy**.

Wait ~30 seconds. Cloudflare will build and deploy.

---

## Step 5 — Site is live (instantly)

Your site is now at:

**`https://everyday-studio.pages.dev`**

(The exact subdomain may have a random suffix the first time — you can rename it later in **Settings → General → Custom domains → pages.dev subdomain**.)

Every time you push a commit to `main`, Cloudflare will redeploy in ~15 seconds. Each branch and pull request also gets its own preview URL — useful for testing changes before going live.

---

## Step 6 (later) — Connect `everydaystudio.com`

Once you've bought the domain:

### If you buy via Cloudflare Registrar (recommended)
1. In Cloudflare dashboard: **Domain Registration → Register Domains**.
2. Search `everydaystudio.com`, buy it (~$10/yr, at cost — no markup).
3. The domain automatically lives on your Cloudflare account.
4. Go to your Pages project → **Custom domains** → **Set up a custom domain** → enter `everydaystudio.com` and `www.everydaystudio.com`.
5. Cloudflare auto-configures the DNS. SSL is automatic. Done.

### If you buy via Porkbun / Namecheap / another registrar
1. Buy the domain there.
2. In your Pages project → **Custom domains** → **Set up a custom domain** → enter `everydaystudio.com`.
3. Cloudflare gives you a CNAME / nameserver instruction.
4. **Recommended:** transfer the domain to Cloudflare later for cheaper renewals (no rush).

---

## Day-to-day workflow

Once everything is connected, your workflow is just:

```bash
# Edit files locally
vim index.html  # or your editor of choice

# Preview locally
python3 -m http.server 8080
# Visit http://localhost:8080

# When happy, commit and push
git add -A
git commit -m "Update hero copy"
git push

# Cloudflare auto-deploys in ~15 seconds.
```

That's it. You'll get a deploy notification email each time.

---

## Troubleshooting

**"Permission denied" on git push**
→ You haven't set up GitHub auth. Use a Personal Access Token (https://github.com/settings/tokens?type=beta) with `repo` scope, paste it when prompted for password.

**Cloudflare build fails**
→ Make sure **Build command** is empty and **Output directory** is empty or `/`. This is a static site, no build step needed.

**Site shows 404**
→ Make sure `index.html` is at the root of the repo (it is), and that the production branch is set to `main`.

**Want to change brand/copy fast**
→ Edit locally, push to `main`, Cloudflare redeploys in ~15 seconds.

---

## What you've gained with this setup

- **Free hosting** (no monthly cost, ever).
- **Free SSL** (https://) automatically.
- **Free CDN** — your site is fast from anywhere in the world.
- **Free deploy previews** for every branch / PR.
- **Auto-deploys** on every git push.
- **Free analytics** if you enable Cloudflare Web Analytics in the Pages settings.
- A real **professional workflow** that scales to your future apps (you can host marketing pages, app landing pages, and API endpoints on the same Cloudflare account).
