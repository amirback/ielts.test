# IELTS Placement Test

A free, self-contained IELTS academic placement test. No backend. No registration. No external libraries.

**Live site → [amirback.github.io/ielts.test](https://amirback.github.io/ielts.test)**

---

## What it does

15 questions across three sections — Grammar, Vocabulary, and Reading Comprehension — calibrated against the CEFR scale. On completion, the user receives an estimated IELTS band score and a level-specific feedback block.

| Section | Questions | Levels tested |
|---|---|---|
| Grammar | 5 | B1 · B2 · C1 |
| Vocabulary | 5 | A2 · B1 · B2 · C1 |
| Reading | 5 | B1 · B2 · C1 |

---

## Scoring

Each question carries a weighted point value based on difficulty:

| CEFR level | Points per correct answer |
|---|---|
| A2 | 1 |
| B1 | 2 |
| B2 | 3 |
| C1 | 4 |

**Maximum score: 41 points.**

| Score range | CEFR result | IELTS band |
|---|---|---|
| 0 – 5 | A2 | ~4.0 |
| 6 – 11 | B1 | ~5.0 – 5.5 |
| 12 – 17 | B2 | ~6.0 – 6.5 |
| 18 – 22 | C1 | ~7.0 – 7.5 |
| 23 – 41 | C1+ | ~8.0+ |

---

## Design

- **Palette:** Black `#0C0C0C` · White `#FFFFFF` · Red `#D90012` — strictly three colours.
- **Typography:** [Inter](https://fonts.google.com/specimen/Inter), weights 400–900.
- **Icons:** Inline SVG only — no icon fonts, no emoji.
- **Layout:** Mobile-first, single column, max-width 640 px.

---

## Internationalisation

The UI ships with English and Russian. Toggle is in the header. Language selection also re-renders the current question if the quiz is in progress.

To add a third language: copy either block in the `i18n` object inside `index.html`, translate the strings, and add a button to the toggle in the header.

---

## Stack

| Concern | Solution |
|---|---|
| Markup | HTML5 |
| Styles | Vanilla CSS (custom properties) |
| Logic | Vanilla ES6+ |
| Fonts | Google Fonts — Inter |
| Dependencies | None |

Everything runs in a single `index.html` file.

---

## Local development

No build step required.

```bash
git clone https://github.com/amirback/ielts.test.git
cd ielts.test
open index.html        # macOS
# or: start index.html  # Windows
# or: xdg-open index.html  # Linux
```

---

## Deployment

The site is hosted on **GitHub Pages** from the `main` branch root.

To deploy your own fork:
1. Fork the repository.
2. Go to **Settings → Pages**.
3. Set source to `main` branch, `/ (root)`.
4. Save. GitHub will publish at `https://<your-username>.github.io/ielts.test`.

---

## Project structure

```
ielts.test/
└── index.html    # entire application — HTML, CSS, JS
```

---

## Customisation

All questions live in the `questions` array in `index.html`. Each entry follows this shape:

```js
{
  id: 1,
  section: 'grammar',       // 'grammar' | 'vocabulary' | 'reading'
  difficulty: 'B1',         // 'A2' | 'B1' | 'B2' | 'C1'
  points: 2,
  question: { en: '...', ru: '...' },
  options:  { en: ['A', 'B', 'C', 'D'], ru: ['А', 'Б', 'В', 'Г'] },
  correct: 1,               // zero-based index into options[]
  passage: true             // optional — set on reading questions
}
```

---

## Licence

MIT — use freely, modify freely, attribute appreciated.
