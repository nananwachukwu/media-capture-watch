# 🚀 Step-by-Step: Deploy Media Capture Watch to GitHub Pages

This guide assumes you're starting from zero. Follow every step in order.

---

## STEP 1 — Install Git (if you don't have it)

### macOS
Open Terminal and run:
```bash
xcode-select --install
```

### Windows
Download and install from: https://git-scm.com/download/win

### Linux
```bash
sudo apt install git
```

**Verify it works:**
```bash
git --version
# Should show something like: git version 2.39.0
```

---

## STEP 2 — Create a GitHub Account

1. Go to https://github.com
2. Click **Sign up**
3. Use your academic email (TCD) — this gives you free GitHub Pro features
4. Complete verification

---

## STEP 3 — Configure Git with Your Identity

Open your terminal and run:

```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@tcd.ie"
```

---

## STEP 4 — Create the Repository on GitHub

1. Go to https://github.com/new
2. Fill in:
   - **Repository name:** `media-capture-watch`
   - **Description:** `Interactive map of Big Tech's funding relationships with journalism`
   - **Visibility:** ✅ Public
   - **Initialize:** Do NOT check any boxes (no README, no .gitignore, no license — we have our own)
3. Click **Create repository**
4. You'll see a page with setup instructions — keep this tab open

---

## STEP 5 — Download the Project Files

Download the project folder from Claude. It contains:

```
media-capture-watch/
├── index.html              ← The visualization
├── data/
│   └── deals.json          ← The dataset (JSON format)
├── docs/
│   ├── METHODOLOGY.md      ← How data was collected
│   └── UPDATING.md         ← How to add new deals
├── CNAME.example           ← Template for custom domain
├── .gitignore              ← Git ignore rules
├── LICENSE                 ← MIT (code) + CC BY-SA 4.0 (data)
└── README.md               ← Project documentation
```

---

## STEP 6 — Initialize Git and Push to GitHub

Open Terminal / Command Prompt. Navigate to the project folder:

```bash
cd ~/Downloads/media-capture-watch
# Or wherever you saved the project folder
```

Run these commands ONE BY ONE:

```bash
# Initialize the git repository
git init

# Add all files
git add .

# Create the first commit
git commit -m "Initial release: Media Capture Watch v1.0"

# Connect to your GitHub repository (replace nananwachukwu)
git remote add origin https://github.com/nananwachukwu/media-capture-watch.git

# Set the branch name
git branch -M main

# Push to GitHub
git push -u origin main
```

**If asked for credentials:** GitHub now requires a Personal Access Token instead of a password.
1. Go to https://github.com/settings/tokens
2. Click **Generate new token (classic)**
3. Give it a name like "media-capture-watch"
4. Check the `repo` scope
5. Click **Generate token**
6. Copy the token and use it as your password when prompted

---

## STEP 7 — Enable GitHub Pages

1. Go to your repository on GitHub: `https://github.com/nananwachukwu/media-capture-watch`
2. Click **Settings** (tab at the top)
3. In the left sidebar, click **Pages**
4. Under **Source**, select:
   - **Deploy from a branch**
   - Branch: **main**
   - Folder: **/ (root)**
5. Click **Save**
6. Wait 1–2 minutes
7. Refresh the page — you'll see:
   > ✅ Your site is live at `https://nananwachukwu.github.io/media-capture-watch/`

**Click the link — your site is now live on the internet!** 🎉

---

## STEP 8 — Update the README

Go back to your local project. Open `README.md` and replace:
- `nananwachukwu` with your actual GitHub username (appears in URLs and links)
- Update the live site link at the top

Then push the update:
```bash
git add README.md
git commit -m "Update README with correct URLs"
git push
```

---

## STEP 9 — (Optional) Add a Custom Domain

If you want a custom domain like `mediacapturewatch.org`:

### 9a. Register a domain
Good registrars for academic/research projects:
- **Cloudflare Registrar** — Cheapest (.org ~$10/year), also gives you a CDN
- **Namecheap** — Good for .org and .watch domains
- **Porkbun** — Affordable, simple interface

Suggested domains:
- `mediacapturewatch.org` (~$10/year)
- `mediacapture.watch` (~$35/year for .watch TLD)

### 9b. Add CNAME file
```bash
# In your project folder:
cp CNAME.example CNAME
# Edit CNAME to contain your domain (no https://, no trailing slash):
echo "mediacapturewatch.org" > CNAME
git add CNAME
git commit -m "Add custom domain"
git push
```

### 9c. Configure DNS at your registrar
Add these DNS records:

**For apex domain (mediacapturewatch.org):**
```
Type: A
Name: @
Value: 185.199.108.153

Type: A
Name: @
Value: 185.199.109.153

Type: A
Name: @
Value: 185.199.110.153

Type: A
Name: @
Value: 185.199.111.153
```

**For www subdomain:**
```
Type: CNAME
Name: www
Value: nananwachukwu.github.io
```

### 9d. Enable HTTPS
1. GitHub Settings → Pages → Custom domain → Enter your domain
2. Check **Enforce HTTPS**
3. Wait up to 24 hours for the SSL certificate to provision (usually ~15 minutes)

---

## STEP 10 — Making Future Updates

Whenever you want to add new deals or make changes:

```bash
# 1. Make your edits to index.html (and optionally data/deals.json)

# 2. See what changed
git status

# 3. Stage changes
git add .

# 4. Commit with a descriptive message
git commit -m "Add: Meta x Associated Press deal (Jan 2026)"

# 5. Push to GitHub (site updates automatically)
git push
```

### Quick edit via GitHub.com (no terminal needed)

1. Go to your repo on GitHub
2. Click on `index.html`
3. Click the pencil icon (✏️) to edit
4. Make your changes
5. Click **Commit changes**
6. Site updates in ~1 minute

---

## Troubleshooting

| Problem | Solution |
|---------|----------|
| Site shows 404 | Wait 2-3 minutes after enabling Pages, or check that `index.html` is in the root |
| Custom domain not working | DNS changes can take up to 48 hours. Check DNS with `dig mediacapturewatch.org` |
| HTTPS not working | Must wait for SSL certificate. Can take up to 24 hours. |
| Fonts not loading | The site uses Google Fonts. They should load automatically. If on a restricted network, fonts will fall back gracefully. |
| Changes not appearing | Hard refresh with Ctrl+Shift+R (or Cmd+Shift+R on Mac) to clear cache |

---

## What's Next?

Once the basic site is live, you can:

1. **Share it** — Post on academic Twitter/Bluesky, share with Berkman Klein and DAIR communities
2. **Add an OG image** — Create a screenshot for social media preview cards
3. **Submit to directories** — Civic Tech Guide, DAIR resources page
4. **Set up Google Analytics** — (Optional) To track visitors without compromising privacy, use Plausible.io or Fathom (privacy-respecting alternatives)
5. **Add a data submission form** — Use Google Forms or Tally.so to let people submit new deals
