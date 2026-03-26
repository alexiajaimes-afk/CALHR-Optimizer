# Job Description Generator — Public Sector

An AI-powered tool for state government HR teams to transform outdated or vague job materials into clean, structured, public-sector-ready job descriptions.

Built with vanilla HTML/CSS/JS. No build step. No dependencies. Opens directly in a browser.

---

## Features

- **AI generation** — Rewrites vague job materials into specific, action-based government HR language
- **Tone slider** — Three settings from Formal/Traditional to Clear & Modern (plain language)
- **Before / after view** — Side-by-side comparison of original materials vs. generated output
- **Civil service classification** — AI-suggested classification codes, series, and grade levels
- **Copy & download** — Copy to clipboard or download as `.txt`
- **Dark mode** — Follows system preference automatically

## Sections generated

1. Job Title (refined and specific)
2. Job Summary (3–4 sentences)
3. Key Responsibilities (5–8 action-based bullets)
4. Minimum Qualifications
5. Preferred Qualifications
6. Skills & Competencies (technical + interpersonal)

---

## Quick start

### 1. Clone the repo

```bash
git clone https://github.com/YOUR_USERNAME/jd-generator.git
cd jd-generator
```

### 2. Add your API key

Copy the example config and add your [Anthropic API key](https://console.anthropic.com):

```bash
cp config.js.example config.js
```

Then edit `config.js`:

```js
const CONFIG = {
  apiKey: 'sk-ant-...'
};
```

> `config.js` is listed in `.gitignore` and will never be committed.

### 3. Open in browser

```bash
open index.html
```

No server required. The tool runs entirely in the browser.

---

## Project structure

```
jd-generator/
├── index.html       # Full application (single file)
├── config.js        # API key — gitignored, never committed
├── .gitignore
└── README.md
```

---

## API key security

This tool calls the Anthropic API directly from the browser using the `anthropic-dangerous-direct-browser-access` header, which is appropriate for **internal / local tools only**.

**Do not deploy this publicly** with a hardcoded API key. For a hosted deployment:
- Build a lightweight backend proxy that holds the key server-side
- Or use a platform like Cloudflare Workers / Vercel Edge Functions as a pass-through

---

## Customization

### Adding departments
Edit the `<select id="department">` options in `index.html`.

### Adjusting tone instructions
Find the `toneInst` object in the `<script>` block and edit the prompt strings for each tone level.

### Changing the model
Search for `claude-sonnet-4-20250514` in `index.html` and replace with another Anthropic model string.

---

## Requirements

- A modern browser (Chrome, Firefox, Safari, Edge)
- An [Anthropic API key](https://console.anthropic.com)

---

## License

MIT — free to use, modify, and distribute.
