<div align="center">

# 🔍 MiMoDetect

**AI vs Human Text Detection — Instant, Private, Zero Dependencies**

Detect AI-generated text with sentence-level highlights and multi-signal analysis

[![Live Demo](https://img.shields.io/badge/Live-Demo-6366f1?style=for-the-badge&logo=vercel&logoColor=white)](https://gyoomei.github.io/mimodetect/)
[![GitHub Stars](https://img.shields.io/github/stars/gyoomei/mimodetect?style=for-the-badge&logo=github&logoColor=white)](https://github.com/gyoomei/mimodetect/stargazers)
[![License](https://img.shields.io/badge/License-MIT-22c55e?style=for-the-badge&logo=open-source-initiative&logoColor=white)](LICENSE)

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![Zero Dependencies](https://img.shields.io/badge/Dependencies-0-22c55e?style=flat-square)
![Client-Side](https://img.shields.io/badge/100%25-Client--Side-6366f1?style=flat-square)
![API Keys](https://img.shields.io/badge/API-Keys%20Not%20Required-22c55e?style=flat-square)

</div>

---

## The Problem

AI-generated text is flooding every platform — emails, essays, social media, job applications. Existing detectors require signup, charge per scan, send your text to remote servers, or take 30+ seconds per analysis.

**MiMoDetect solves all four.** Paste text → instant result. No account. No data leaves your browser. Under 1 second.

---

## How It Works

```
┌─────────────────────────────────────────────────────┐
│  INPUT: Paste any text (20+ chars)                  │
└──────────────────────┬──────────────────────────────┘
                       │
                       ▼
┌─────────────────────────────────────────────────────┐
│  ENGINE 1: Heuristic Analysis (<100ms, offline)     │
│  ┌───────────────────────────────────────────────┐  │
│  │ • 40+ AI vocabulary markers                   │  │
│  │ • 30+ human colloquial expressions            │  │
│  │ • Transition phrase detection                 │  │
│  │ • Sentence length uniformity (CV analysis)    │  │
│  │ • Type-token vocabulary diversity ratio       │  │
│  │ • Personal pronoun frequency                  │  │
│  │ • Contraction / emoji / exclamation density   │  │
│  │ • Average word length analysis                │  │
│  └───────────────────────────────────────────────┘  │
│                        │                             │
│                        ▼                             │
│  ┌───────────────────────────────────────────────┐  │
│  │ WEIGHTED SCORE: 0-100% AI probability         │  │
│  │ SENTENCE-LEVEL: each line tagged AI/Human/±   │  │
│  └───────────────────────────────────────────────┘  │
└──────────────────────┬──────────────────────────────┘
                       │
          ┌────────────┴────────────┐
          ▼                         ▼
   ⚡ INSTANT OUTPUT         🧠 AI VERIFY (optional)
   (heuristic only)          (GPT-OSS 20B via
                              Pollinations.ai,
                              45s timeout, fallback
                              to heuristic)
```

---

## Features

**Dual-Engine Architecture**
- ⚡ **Heuristic Engine** — 10 signal rules, runs instantly client-side, works offline
- 🧠 **AI Verification** — optional second opinion from GPT-OSS 20B (free API, no key needed)

**5 Diagnostic Metrics**
| Metric | What It Measures |
|--------|-----------------|
| 🎯 Predictability | How predictable/patterned the text structure is |
| 📚 Vocab Diversity | Unique word ratio (type-token ratio) |
| 🔄 Sentence Variety | Variation in sentence lengths (coefficient of variation) |
| 💬 Personal Voice | Presence of personal pronouns and subjective language |
| 🏗️ Coherence | Structural transitions and logical flow |

**Sentence-Level Analysis**
Every sentence is color-coded:
- 🔴 **AI Suspect** — formal vocabulary, uniform structure, transition phrases
- 🟢 **Human Signal** — slang, contractions, emoji, personal pronouns
- 🟡 **Uncertain** — ambiguous patterns

**Signal Detection**
Real-time list of detected signals:
- Formal/academic word count
- Transition phrase frequency
- Sentence length uniformity
- Colloquial expression presence
- Contraction and emoji density

---

## Quick Start

**Option 1: Use the live demo**
→ [gyoomei.github.io/mimodetect](https://gyoomei.github.io/mimodetect/)

**Option 2: Run locally**
```bash
git clone https://github.com/gyoomei/mimodetect.git
cd mimodetect
open index.html
```

That's it. No build step. No `npm install`. No server.

---

## Sample Texts

Three built-in samples for testing:

| Sample | Description |
|--------|-------------|
| 🤖 AI Text | Formal academic paragraph with transition phrases and uniform structure |
| ✍️ Human Text | Casual first-person narrative with slang, emoji, and irregular structure |
| 🎭 Mixed Text | Blend of formal AI patterns and personal human voice |

---

## Tech Stack

```
Frontend:    Pure HTML + CSS + JavaScript
Styling:     CSS custom properties, glassmorphism, animated mesh gradient
Fonts:       Geist + Geist Mono (Google Fonts)
AI Engine:   Heuristic (client-side) + GPT-OSS 20B (Pollinations.ai free API)
Storage:     localStorage for history + stats
Deploy:      GitHub Pages (single file, zero backend)
```

**Zero dependencies. Zero build tools. Zero API keys required.**

---

## Architecture

```
mimodetect/
└── index.html          ← everything in one file (37KB)
    ├── CSS             ← dark/light themes, glassmorphism, particles
    ├── Heuristic       ← 10-rule detection engine
    ├── Display         ← score ring, metrics, sentence highlights
    ├── AI Verify       ← Pollinations.ai integration (optional)
    ├── History         ← localStorage persistence
    └── Stats           ← global counter
```

---

## Why Heuristic + AI Hybrid?

| Approach | Speed | Privacy | Accuracy |
|----------|-------|---------|----------|
| API-only detectors | 10-30s | ❌ Text sent to server | High |
| Rule-only detectors | Instant | ✅ Fully private | Medium |
| **MiMoDetect hybrid** | **<1s instant** | **✅ Private by default** | **High** |

The heuristic engine handles 90% of cases instantly. AI verification is a bonus for edge cases — and it gracefully falls back to heuristic if the API times out.

---

## Contributing

1. Fork the repo
2. Edit `index.html` (it's the only file)
3. Test locally by opening the file in a browser
4. Submit a PR

All logic lives in a single file. No build pipeline. No configuration.

---

<div align="center">

**Built with heuristic analysis + GPT-OSS 20B**

[Live Demo](https://gyoomei.github.io/mimodetect/) · [Report Bug](https://github.com/gyoomei/mimodetect/issues) · [Request Feature](https://github.com/gyoomei/mimodetect/issues)

</div>
