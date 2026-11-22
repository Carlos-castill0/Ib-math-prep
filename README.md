# IB Mental Math

A mental-math trainer for investment-banking interviews. It is one file (`index.html`) with inline CSS and JavaScript. There is no framework, no build step and no backend. It is built for a phone browser.

**Live:** https://carlos-castill0.github.io/Ib-math-prep/ (after GitHub Pages is enabled, see below)

## What's inside

| # | Category | Examples | Accepted |
|---|----------|----------|----------|
| 1 | Percent of a number | 6% of 18,000 · 17.5% of 240 · "54 is what % of 360?" · "12% of what is 4,800?" | exact |
| 2 | Multiplication | 47 × 6 · 38 × 24 · 45 × 8,000 · 2.5 × 36,000 | exact |
| 3 | Fractions ↔ percents | 3/8 as a % · 83.33% = ?/6 · 9.09% ≈ 1/? | ±0.1 pt |
| 4 | Growth & CAGR | 100 → 150 in 3 years, CAGR? · 200 growing 10% for 3 years | ±0.5 pt / ±0.5% |
| 5 | Valuation multiples | EBITDA $45M at 8.5x → EV · reverse multiple · equity bridge · share price | exact (±0.1x for messy reverses) |
| 6 | Rule of 72 / IRR | 2x in 5 years → IRR · years to double at 8% · MOIC needed for 20% over 5 yrs | IRR ±1 pt · years ±4% · MOIC ±2% |
| 7 | Margins | Revenue 320, EBITDA 56 → margin · bps change · net income bridge | exact (±0.2 pt for messy) |
| 8 | Paper LBO steps | equity check · debt paydown · cash sweep · MOIC from entry/exit EV and net debt | exact (MOIC ±0.05x) |

Each category has three difficulty levels: 1 = warm-up, 2 = interview level, 3 = stretch.

**Modes:**
- **Sprint:** 2 minutes, mixed categories.
- **Drill:** one category, 20 questions.
- **Weakness:** 20 questions, weighted toward your least accurate and slowest categories (it uses your last 40 attempts in each category).

**Answers:** the input accepts `1,080`, `8.5x`, `45M`, `$1.2bn`, `14.5%`, `0.145` (for 14.5%), `150bps` and `3/8`. Enter submits.

**Feedback:** every answer shows the exact value and your time. A wrong answer also shows a one-line shortcut.

## Your data

History is stored in this browser's `localStorage` only. Nothing is sent anywhere. Use **Stats → Export JSON** for a backup and **Import** to restore or merge one. If the browser blocks storage, the app still works and shows a warning.

## Self-test

Open `index.html?test` (or `…/Ib-math-prep/?test`). It runs about 300k checks in the browser:
- **Parser and grader:** a fixed table of input cases.
- **Generators:** for each of the 8 categories × 3 difficulties, 1,000 problems. Every answer is recomputed independently from the numbers printed in the question.
- **Tolerances:** each problem's displayed answer must be accepted, and a wrong answer must be rejected.
- **Shortcuts:** each shortcut must land on the answer.
- **Data logic:** Weakness weighting, stats, import/merge sanitising, and recovery from storage failure.

`?test&seed=123&n=3000` reproduces a run and makes it larger.

## Enable GitHub Pages (one time)

Settings → Pages → Build and deployment → Source: **Deploy from a branch** → pick this repo's default branch and `/ (root)` → Save. The site appears at the URL above within a minute or two.
