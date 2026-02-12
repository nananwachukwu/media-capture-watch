# How to Update the Data

This guide walks through adding new deals, companies, or corrections to the dataset.

## Adding a New Deal

### Step 1: Open `index.html`

Open the file in any text editor (VS Code, Sublime Text, or even GitHub's web editor).

### Step 2: Find the deals array

Search for `const deals=[` — this is where all the data lives.

### Step 3: Add your entry

Copy this template and fill in the values:

```javascript
{c:"COMPANY",p:"Program Name",t:"Deal Type",a:"Amount",y:2025,r:"Recipient1, Recipient2",d:"Brief description",ai:1},
```

**Field reference:**

| Field | Type | Example | Notes |
|-------|------|---------|-------|
| `c` | String | `"OpenAI"` | Must match a key in the `COLORS` object |
| `p` | String | `"NYT Content Deal"` | Official program name |
| `t` | String | `"Content License"` | See deal types below |
| `a` | String | `"$50M/year"` | Use `"Undisclosed"` if unknown |
| `y` | Integer | `2025` | Year announced (no quotes) |
| `r` | String | `"New York Times, WSJ"` | Comma-separated recipients |
| `d` | String | `"Multi-year content licensing"` | Brief factual description |
| `ai` | Integer | `1` | `1` = AI-related, `0` = not |

### Step 4: Commit and push

```bash
git add index.html
git commit -m "Add: OpenAI x NYT content deal (2025)"
git push
```

The site updates automatically within ~1 minute.

---

## Standard Deal Types

Use these existing categories when possible for consistency:

- `Content License` — Paying for content access/usage rights
- `Grant` / `Grants` — Direct financial grants
- `Grant + Credits` — Cash plus platform credits (API, cloud, etc.)
- `Grants + Training` — Financial support plus training programs
- `Revenue Share` — Ongoing revenue-sharing arrangement
- `Technology Partnership` — Non-financial tech collaboration
- `Multiple Programs` — Umbrella programs with mixed types
- `Innovation Fund` — Competitive funding programs
- `Content License + Funding` — Licensing plus direct investment
- `Training + Credits` — Training programs plus platform credits
- `Grant Partner` — Co-funding arrangement

---

## Adding a New Company

### Step 1: Add a color

Find the `COLORS` object near the top of the JavaScript section:

```javascript
const COLORS={OpenAI:'#10a37f',Google:'#4285f4', ...
```

Add your new company:

```javascript
const COLORS={OpenAI:'#10a37f',Google:'#4285f4', ... ,'NewCompany':'#ff00ff'};
```

**Choosing a color:** Use the company's brand color. Check [brandcolors.net](https://brandcolors.net) for official hex values. Ensure it's visually distinct from existing colors.

### Step 2: Add deals

Add one or more deals for the new company (see above).

### Step 3: Update the periods array (if needed)

If your deal predates 2015, add the year to the `PERIODS` array:

```javascript
const PERIODS=['2014','2015','2016', ...
```

---

## Making Corrections

1. Find the incorrect entry in the `deals` array
2. Edit the relevant field
3. Commit with a descriptive message:

```bash
git commit -m "Fix: Correct OpenAI-AP deal amount to $XX"
```

---

## Updating via GitHub Web Interface

If you're not comfortable with git:

1. Go to the repository on GitHub
2. Click on `index.html`
3. Click the pencil icon (✏️) to edit
4. Make your changes
5. Scroll down, add a commit message, and click "Commit changes"

---

## Also Update `data/deals.json`

The `data/deals.json` file is the machine-readable version of the dataset for researchers and developers. When adding deals to `index.html`, also add them to this JSON file in the expanded format:

```json
{
  "company": "OpenAI",
  "program": "New Program Name",
  "type": "Content License",
  "amount": "$50M",
  "year": 2025,
  "recipients": "Publisher Name",
  "description": "Description here",
  "ai_related": true,
  "source": "https://source-url.com/article"
}
```
