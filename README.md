# Media Capture Watch

**An interactive map revealing Big Tech and AI companies' funding relationships with journalism and media organizations.**

[![License: CC BY-SA 4.0](https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-sa/4.0/)
[![Data: 65+ deals](https://img.shields.io/badge/Deals%20Tracked-65%2B-ff3b30)]()
[![Last Updated](https://img.shields.io/badge/Updated-February%202026-blue)]()

[**→ View Live Site**](https://nananwachukwu.github.io/media-capture-watch/) · [**→ Download Data (JSON)**](data/deals.json) · [**→ Report an Issue**](../../issues)

---

## What is this?

Media Capture Watch is an interactive data visualization that maps the funding relationships between 13 technology companies and hundreds of media organizations worldwide. It tracks 65+ deals worth over $1 billion, revealing the emerging architecture of media capture. My PhD research at Trinity College Dublin's AI Accountability Lab examines how AI platforms construct and maintain power not just through content control, but through controlling the very conditions under which they can be held accountable. I study this across three dimensions in what I call the trident which [I will explain in a different repository]. Media capture is one fork that looks at accountability failure at the level of the information ecosystem. The question driving this fork is somewhat simple. I'm asking what happens to public scrutiny of tech companies when those same companies are funding the institutions responsibile for their scrutiny?

Media capture traditionally describes how governments or political elites gain control over media through ownership, regulatory pressure, adverts or even by installing a loyal editorial lead. So many scholars have written about this from various angles. The European Meadia Freedom ACt adopted in April 2024, explicitly names this as a risk in Recital 30 however, it describes how captures public service media providers distort competition when they provide imbalanced reporting while being subsidised by the state. The EMFA was designed for a threat model in which the state is the primary captor. The transparency obligations in it target public funds while the editorial safeguards address political interference. There is no equivalent framework for private technology companies that are funding journalism at comparable or greater scale, while simultaneously operating the platforms through which that journalism reaches its audience, and building the AI systems that may eventually replace it.

**What this visualisation maps**

Media Capture Watch documents over $1Bn in funding relationships between major technology companies and journalism organisations worldwide. Every connection is sourced from public records.
I want to be precise about what I am **NOT** arguing. I am **not** saying that every journalist who attends a Google-funded workshop is compromised, or that every newsroom accepting a Meta grant produces favourable coverage. That manner of crude transactional analysis misses the point entirely. Media capture, in its most effective form, does not work through editorial directives. It works through the gradual reshaping of institutional incentives, professional norms, and the boundaries of what feels natural to report. Simply speaking, it works through creating a culture of dependency.

A technology company creates a funding programme for journalism. It does not tell editors what to write. It does not need to. It becomes a stakeholder in the financial survival of the outlets it funds. It sponsors conferences where journalists and technologists share stages as peers rather than as subject and scrutineer. It embeds its tools into newsroom workflows offering credits in large quantities. It trains journalists on its products. Over time, the funder becomes part of the furniture. I am arguing that the question every journalist should be asking is 'what is this company doing to the information environment?'. If it becomes harder to ask, because the institutional architecture makes asking feel ungrateful, adversarial, or beside the point, then you could have the answer.

**What I ask of you**

This visualisation does not tell you what to conclude. It gives you the information to ask better questions. When you see a single company funding training programmes, innovation grants, content licensing, and industry conferences across dozens of countries simultaneously, you can decide for yourself whether that is a healthy funding environment or a structural dependency. When you see the same companies funding journalism and operating the distribution infrastructure for that journalism, you can assess whether the existing regulatory framework is adequate.
All I ask is that we take corporate capture of journalism as seriously as we take state capture. That we apply the same analytical frameworks, the same institutional safeguards, and the same investigative energy to understanding how technology companies shape the conditions of public knowledge as we do to governments and other sectors.

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
