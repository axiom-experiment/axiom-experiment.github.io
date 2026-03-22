# GitHub Pages Deployment Instructions

## One-Time Setup (5 minutes)

### Step 1: Create the GitHub repo

```bash
# Replace GITHUB_USERNAME with your actual GitHub username/org (e.g. axiom-dev)
GITHUB_USERNAME="axiom-dev"

# Create a new public repo named [username].github.io
# Go to: https://github.com/new
# Repository name: axiom-dev.github.io  (MUST match username exactly for apex URL)
# Visibility: Public
# Click "Create repository"
```

### Step 2: Push this website to the repo

Open a terminal/command prompt and run:

```bash
# Navigate to the website folder
cd "C:\Users\User\Desktop\claude-workspace\axiom\code\website"

# Initialize git
git init
git add .
git commit -m "Deploy AXIOM website to GitHub Pages"

# Add your remote (replace axiom-dev with your actual username)
git remote add origin https://github.com/axiom-dev/axiom-dev.github.io.git

# Push
git branch -M main
git push -u origin main
```

### Step 3: Enable GitHub Pages

1. Go to your repo on GitHub: `https://github.com/axiom-dev/axiom-dev.github.io`
2. Click **Settings** → **Pages** (left sidebar)
3. Under **Source**, select **GitHub Actions**
4. The workflow in `.github/workflows/deploy.yml` will automatically run
5. Wait ~2 minutes for deployment

### Step 4: Your site is live at:

```
https://axiom-dev.github.io
```

Save this URL: it's your Stripe business website URL.

---

## Step 5: Update Stripe with your website URL

1. Go to: https://dashboard.stripe.com/settings/account
2. Find the **Business website** field
3. Enter: `https://axiom-dev.github.io`
4. Save changes

This unlocks full Stripe live payment capabilities.

---

## Save the deployment URL

Save to: `C:\Users\User\Desktop\claude-workspace\axiom\config\website_url.txt`

Content: `https://axiom-dev.github.io`

---

## Notes

- Replace `axiom-dev` with the actual GitHub username/org used
- The GitHub Actions workflow auto-deploys on every push to main
- Site is pure HTML — no build step, no Node.js required on the server
- After first deploy, any future updates just require `git push`
