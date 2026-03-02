# 🔴 Media Capture Watch

**An interactive map revealing Big Tech and AI companies' funding relationships with journalism and media organizations.**

[![License: CC BY-SA 4.0](https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-sa/4.0/)
[![Data: 65+ deals](https://img.shields.io/badge/Deals%20Tracked-65%2B-ff3b30)]()
[![Last Updated](https://img.shields.io/badge/Updated-February%202026-blue)]()

[**→ View Live Site**](https://nananwachukwu.github.io/media-capture-watch/) · [**→ Download Data (JSON)**](data/deals.json) · [**→ Report an Issue**](../../issues)

---

## What is this?

Media Capture Watch is an interactive data visualization that maps the funding relationships between 13 technology companies and hundreds of media organizations worldwide. It tracks 65+ deals worth over $1 billion, revealing the emerging architecture of media capture.

**Key findings:**
- Over 90% of 2025 deals are explicitly AI-related (content licensing for LLMs, chatbots, AI search)
- OpenAI alone has 21 tracked deals with major publishers
- Google has committed >$300M globally since 2018
- A fundamental shift from philanthropy-style grants to commercial content extraction

**Features:**
- 🕸️ **Network view** — Interactive force-directed graph of all relationships
- 📊 **Flow view** — Sankey-style visualization of funding flows by type
- ⏱️ **Timeline** — Animate the growth from 2015 to 2025
- 🔍 **Search & filter** — Find any entity, filter by company
- 📱 **Mobile responsive** — Works on phones and tablets
- 🔒 **Privacy-first** — No cookies, no tracking, no external requests beyond fonts

## Screenshots

*Network view showing the web of relationships between tech companies and media organizations*

---

## Quick Start

**View online:** [nananwachukwu.github.io/media-capture-watch](https://nananwachukwu.github.io/media-capture-watch/)

**Run locally:**
```bash
git clone https://github.com/nananwachukwu/media-capture-watch.git
cd media-capture-watch
open index.html          # macOS (or xdg-open on Linux, start on Windows)
```

No build tools, no dependencies, no server required.

---

## Project Structure

```
media-capture-watch/
├── index.html           # The visualization (everything in one file)
├── data/
│   └── deals.json       # The dataset (for reference/download/API use)
├── docs/
│   ├── METHODOLOGY.md   # Data collection methodology
│   └── UPDATING.md      # How to add new deals
├── LICENSE              # CC BY-SA 4.0
└── README.md            # This file
```

---

## How to Update the Data

The dataset lives inside `index.html` in the JavaScript `deals` array. Each deal is a simple object:

```javascript
{
  c: "OpenAI",              // Company name (must match COLORS keys)
  p: "Reuters Deal",         // Program name
  t: "Content License",      // Deal type
  a: "$50M/year",           // Amount (string — use "Undisclosed" if unknown)
  y: 2025,                  // Year (integer)
  r: "Reuters",             // Recipients (comma-separated string)
  d: "Real-time news feed",  // Description
  ai: 1                     // AI-related? (1 = yes, 0 = no)
}
```

**To add a new deal:**
1. Open `index.html`
2. Find the `deals` array (search for `const deals=[`)
3. Add a new entry following the format above
4. Commit and push — the site updates automatically

**To add a new company:**
Add both a color entry and deals:
```javascript
// In the COLORS object:
'NewCompany': '#hexcolor',

// In the deals array:
{c:"NewCompany", p:"Program Name", t:"Content License", a:"$10M", y:2025, r:"Partner", d:"Description", ai:1},
```

See [docs/UPDATING.md](docs/UPDATING.md) for detailed instructions.

---

## Hosting

This site is designed to be hosted for free on **GitHub Pages**:

1. Push this repository to GitHub
2. Go to **Settings → Pages → Source** → Deploy from branch → `main` → `/ (root)`
3. Your site is live at `https://yourusername.github.io/media-capture-watch/`

For a custom domain (e.g., `mediacapturewatch.org`):
1. Register a domain (~$10/year)
2. Add a `CNAME` file to the repo root containing your domain
3. Configure DNS at your registrar (CNAME → `yourusername.github.io`)
4. Enable HTTPS in GitHub Pages settings

---

## Contributing

Contributions are welcome! Ways to help:

- **Add missing deals** — Open a PR or issue with source URL
- **Correct errors** — If any data is inaccurate, please flag it
- **Improve the visualization** — Feature suggestions and code contributions welcome
- **Translate** — Help make this accessible in more languages

Please include a **source URL** for any new data.

---

## Citation

If you use this dataset or visualization in your research, please cite:

```
Media Capture Watch (2026). Mapping Big Tech's Influence on Journalism.
https://github.com/nananwachukwu/media-capture-watch
```

---

## Credits

**Research & Data:** Nana Nwachukwu — Trinity College Dublin

**Inspired by:** [Surveillance Watch](https://surveillancewatch.io) (DAIR Institute)

**Sources:** Digiday, Press Gazette, Columbia Journalism Review (Tow Center), CB Insights, AI Watch Dog, Lenfest Institute, American Journalism Project, and official company announcements.

---

## License

- **Data:** [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/)
- **Code:** [MIT](LICENSE)
