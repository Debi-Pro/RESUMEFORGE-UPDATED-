# ⚡ ResumeForge

> **Next-gen, AI-powered, ATS-optimized resume builder — runs entirely in your browser. Zero sign-up, zero backend.**

![ResumeForge](https://img.shields.io/badge/version-1.0.0-6c63ff?style=flat-square) ![License](https://img.shields.io/badge/license-MIT-00d4ff?style=flat-square) ![HTML](https://img.shields.io/badge/built%20with-HTML%2FCSS%2FJS-00ff88?style=flat-square)

---

## 🚀 What is ResumeForge?

ResumeForge is a single-file resume builder that gives you a real-time ATS score, job-description keyword matching, three professional templates, and export options — all without installing anything or creating an account. Open the `.html` file in any browser and start building.

---

## ✨ Features

| Feature | Description |
|---|---|
| 🤖 **Live ATS Score Engine** | Scores your resume 0–100 in real time based on completeness, keywords, quantified achievements, and formatting |
| 🎯 **JD Keyword Matcher** | Paste any job description and instantly see which keywords your resume is missing vs. matched |
| ⚡ **3 Stunning Templates** | **Forge** (dark hero header), **Nova** (two-column editorial), **Ghost** (minimal typographic) |
| 📥 **4 Export Formats** | PDF via Print, raw HTML, plain text (for ATS portals), and JSON (to save & resume later) |
| 🎨 **8 Accent Colors** | Instantly recolor all templates — Forge Purple, Cyan, Rose, Gold, Mint, Ember, Midnight, Crimson |
| 🧠 **AI Insights Panel** | Context-aware tips that update as you type — flags missing metrics, weak summaries, and more |
| 📊 **Completion Tracker** | Per-section progress bars so you always know what's left to fill in |
| 💾 **Auto-save** | Drafts are saved to `localStorage` every 4 seconds — your work survives a page refresh |

---

## 🗂 Project Structure

```
ResumeForge_fixed.html   ← entire app, single self-contained file
README.md                ← you are here
```

No dependencies, no build step, no node_modules.

---

## 🏁 Getting Started

```bash
# Clone or download
git clone https://github.com/yourname/resumeforge.git
cd resumeforge

# Open in browser (no server needed)
open ResumeForge_fixed.html
# or just double-click the file
```

That's it. Nothing to install.

---

## 🖥 Layout Overview

The app is split into three fixed panels inside a `100vh` viewport:

```
┌──────────────┬──────────────────────────┬─────────────────┐
│   EDITOR     │       PREVIEW            │   SIDEBAR       │
│   300px      │       flex: 1            │   195px         │
│              │                          │                 │
│  7 tabs:     │  Live resume render      │  Completion     │
│  Basics      │  Auto-scaled to fit      │  AI Insights    │
│  Summary     │  Zoom +/− controls       │  Accent Color   │
│  Experience  │  Template switcher       │  Job Match      │
│  Education   │                          │                 │
│  Skills      │                          │                 │
│  Projects    │                          │                 │
│  ATS ✦       │                          │                 │
└──────────────┴──────────────────────────┴─────────────────┘
```

The resume preview auto-scales on load and window resize so the full A4 document always fits inside the available space without horizontal scroll.

---

## 📐 ATS Scoring Breakdown

The ATS engine runs entirely in JS — no API calls. Score is calculated out of 100:

| Check | Points |
|---|---|
| Name present | +5 |
| Email + phone filled | +8 / +5 |
| Location filled | +4 |
| Job title filled | +5 |
| Professional summary (60+ words) | +12 |
| Work experience (1 entry / 2+ entries) | +8 / +5 |
| Quantified achievements (numbers in bullets) | +12 |
| 5+ technical skills | +8 |
| 10+ total skills | +5 |
| Education listed | +6 |
| ATS keywords matched (up to 12) | +1 each |

---

## 🎨 Templates

### Forge
Dark gradient header with purple-to-cyan accent line. Two-column layout: main content left, skills + education sidebar right. Best for tech / engineering roles.

### Nova
Clean white header with a bold bottom border. Symmetrical two-column body. Last name rendered in accent color. Best for design, product, and business roles.

### Ghost
Pure typographic minimalism. Monospace date columns, hairline dividers, zero decoration. Best for senior/principal roles or academic CVs.

---

## 💾 Export Options

| Format | Use case |
|---|---|
| **PDF (Print)** | Most ATS-friendly. Opens browser print dialog — save as PDF. |
| **HTML** | Editable source file. Open in any browser or host online. |
| **Plain Text** | For copy-pasting into online ATS portals (LinkedIn Easy Apply, Workday, etc.) |
| **JSON** | Saves all your resume data so you can reload it later via the auto-save system. |

---

## 🔧 Customization

All design tokens live in `:root` CSS variables at the top of the file:

```css
:root {
  --editor-w: 300px;    /* editor panel width */
  --sidebar-w: 195px;   /* right sidebar width */
  --nav-h: 52px;        /* navbar height */
  --p: #6c63ff;         /* primary accent */
  --cyan: #00d4ff;
  --green: #00ff88;
  /* ... */
}
```

To add a new template, create a `.tpl-yourname` CSS block and a `renderYourName(doc)` JS function, then add a button to the `.tpl-switcher` in the HTML.

---

## 🤝 Contributing

1. Fork the repo
2. Make your changes in `ResumeForge_fixed.html`
3. Test in Chrome, Firefox, and Safari
4. Open a PR with a short description of what you changed

Since this is a single-file app, keep all changes self-contained — no external scripts, no build tools.

---

## 📄 License

MIT — do whatever you want with it. A star on the repo is appreciated. ⭐

---

*Built with HTML, CSS, and vanilla JS. No frameworks, no bundlers, no cloud. By DEBIPRASAD MISHRA*
