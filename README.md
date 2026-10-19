# QFTM-1024

**Quadrotomy Factor Typology Model** — a scientific personality typing system built on the Big Five (IPIP-NEO facets), producing **1024 unique profiles** instead of MBTI's 16.

🌐 **Live demo:** https://Daniil-Myagkov.github.io/qftm-1024/

---

## Why QFTM-1024

| Criterion | MBTI | Raw Big Five | **QFTM-1024** |
|-----------|------|--------------|----------------|
| Profiles | 16 | none (scores only) | **1024** |
| Neuroticism | ignored | recognized | **4 zones tracked** |
| Spectrum | dichotomy | percentages | **quadrotomy per factor** |
| Scientific base | weak (Jung 1920s) | gold standard | **Big Five + readable letters** |
| Test included | no | no | **yes — 120 items, in-app** |
| Change over time | fixed type | recognized | **recognized AND logged in calendar** |

Each of the five factors is split into four zones — `0–30`, `31–50`, `51–70`, `71–100` — giving `4⁵ = 1024` combinations. Every profile maps to one of 16 MBTI-genus families (64 profiles each).

## Features

- 📝 **Built-in 120-item test** — a self-contained Big Five assessment adapted from the public-domain IPIP-NEO-120 (Johnson, 2014). 120 statements on a 1–5 Likert scale, scored in-app into 30 facet scales (0–100) and 5 domain scores, then mapped to your QFTM code and cat. Available in all 5 languages. Includes an explicit self-assessment instruction (*“rate yourself as you are now, not as you wish to be”*) to protect validity. No external site, no redirect, no account — the whole instrument lives in the single HTML file.
- ⚡ **Quick mode** — 5 sliders for instant typing (starts at zero, no preset profile).
- 📋 **Full mode** — all 30 IPIP-NEO facet scales entered by hand, also starting clean at zero. Useful if you already hold facet scores from any validated IPIP-NEO instrument.
- 📅 **Dynamic calendar** — save your profile month by month, watch it evolve.
- 📈 **30-scale graph** — overlay any subset of facets across months.
- 🧬 **16 families explorer** — browse every genus and its 64 members.
- 🐱 **Procedural cat avatars** — coat color = exact profile hue; scene = Conscientiousness, tail/ears = Extraversion, eyes = Agreeableness, face = Neuroticism, object = Openness. Name-stamp supported. Custom pixel-cat favicon included.
- ❤️ **Compatibility module** — two partners' codes produce side-by-side cats, axis breakdown, and **five research-grounded formulas**:
  - **UF-1** Assortative similarity / value congruence *(Youyou et al., 2017)*
  - **UF-2** Complementarity & dominance reciprocity *(Tiedens & Fragale, 2003)*
  - **UF-3** Vulnerability–Stress–Adaptation *(Karney & Bradbury, 1995)*
  - **UF-4** Co-regulation & repair-attempt floor *(Gottman & Levenson, 2000)*
  - **UF-5** Niche construction & life-strategy alignment *(Scarr & McCartney, 1983)*

  Final score synthesized as **QCI** with verdict band. Axis values deterministically recovered from zone midpoints (`15 / 40 / 60 / 85`).
- 🧠 **Schulte table** (3×3 … 12×12) with optional red fixation dot, timer, leaderboards per cat and global.
- 🎮 **ColorMemory** (Simon-style sequence game, 3 speeds) and **ColorShape** (find matching shape/color among 4 strictly unique options drawn from 8 distinct colors × 6 shapes).
- 🌍 **5 languages**: English, Русский, Español, Français, 中文.
- 📱 Fully responsive, mobile-first, Android-friendly. Single-file SPA, zero dependencies.
- 🔒 **Privacy by design** — all data, including test answers and results, lives in your browser's `localStorage`. No backend, no tracking, no accounts, no network calls during the test. Export/import JSON provided for backup and sharing.

## How to use

1. Open the live demo link above in any modern browser (or download `index.html` and double-click it locally — no server needed).
2. Go to the **📝 Test 120** tab (it opens first) and answer all 120 statements honestly, rating yourself as you are *now*. Press **Calculate and save** — your 30 facet scales, 5 domain scores, QFTM code, cat avatar, and calendar entry are produced instantly, all on-device.
   - *Already have facet scores from another IPIP-NEO instrument?* Skip the test and enter them directly in the **📋 30 scales** tab (or estimate the 5 axis averages in **⚡ Quick**).
3. Explore compatibility, dynamics, mini-games, and the 1024-profile map.

## Known rough edges (v5.0)

- Schulte table digits render slightly small on some mobile screens (readable, just compact). Cosmetic fix planned for v5.1.
- Quick-tab sliders do not persist their draft positions across page reloads (only saved results persist). Draft autosave planned for v5.1.

Everything else is production-ready.

## Architecture notes

- Pure client-side HTML/CSS/JS in one file (~6000 lines uncompressed).
- The built-in test follows the IPIP-NEO-120 keying structure (Johnson, 2014): facet assignment is computed from item index by formula and cross-checked by an in-app validator, so a mis-mapped item cannot silently corrupt a profile. Raw IPIP items are public domain; the multilingual wording is an original adaptation.
- Profile color derived from `(iE·64 + iO·16 + iA·4 + iC)/256 · 360°` hue, lightness shifted by neuroticism zone.
- Cat SVG generated procedurally per code; PNG export via canvas rasterization; Web Share API used when available.
- SHA-256 configuration hash exposed in the Rights modal for integrity verification (recomputed dynamically from the canonical source string on each load).
- SEO: rich `<meta>`, Open Graph, Twitter Card, and canonical URL embedded in `<head>` for search engines and AI crawlers.

## License & authorship

© 2026 **Daniil Vasilievich Myagkov** (Мягков Даниил Васильевич). All rights reserved.

You may host and share this unmodified file with the intact authorship notice. You may NOT claim authorship. Commercial use, paid redistribution, and closed derivatives require written permission from the author. Full terms embedded in the app under **⚖️ Rights** and in the repository `LICENSE` file.

This is intentionally **not** an MIT/Apache/GPL project — the authorship and usage boundaries are part of the work itself. The built-in test items are an adaptation of public-domain IPIP content; the surrounding code, scoring logic, cat generator, and all translations are the author's original work.

---

*Built because typology deserves better than 16 boxes — and a test that doesn't send you anywhere else to take it.*
