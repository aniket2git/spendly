# Modern Web Development PYQ — Zero to Full Marks

A complete, concept-first study guide for the previous-year web development question paper.
Built for a reader with **no prior knowledge** of the subject: every concept is taught from
scratch before any question is attempted.

## Files

| File | What it is |
|---|---|
| `WebDev_PYQ_Complete_Guide.pdf` | The study book — 84 pages, A4, print-ready |
| `solution.html` | The source the PDF is generated from |
| `README.md` | This file |

## What's inside

**Part A — Concept building (19 chapters).** Each concept starts with the plain rule, then a
real-life "kid story" analogy, then a diagram, then the traps examiners set.

1. Objects, `this`, and "who is calling me?"
2. `call` / `apply` / `bind`
3. Value vs reference — the copy trap
4. `map` / `filter` / `reduce`
5. Classes, prototype chain, `instanceof`
6. Sync vs async — the event loop
7. Promises — the complete 8-rule chain rulebook
8. `fetch` and the 404 surprise
9. localStorage vs sessionStorage vs cookies
10. Vue basics, `v-if` vs `v-show`
11. `computed` vs `methods` vs `watch` (caching + dependency tracking)
12. Components — props down, events up (`$emit`)
13. Vue Router — params, nested routes, the component-reuse gotcha
14. Vuex — state, mutations, actions, getters
15. Redis
16. Celery + Redis background jobs
17. Webhooks
18. Web security — password hashing, XSS, CSRF, cookie flags
19. Git branches and merging

**Part B — All 32 questions solved.** Every question gets: the original code, all options with
the correct one highlighted, a numbered reasoning trail, and an explanation of *why each wrong
option is wrong*.

**Part C — Answer key and revision sheet.** A one-page key for all 32 questions, the 24 traps the
paper is built from, and a night-before cram sheet organised by topic.

## Answer key (quick reference)

| Q | Answer | Q | Answer | Q | Answer | Q | Answer |
|---|---|---|---|---|---|---|---|
| 1 | D | 9 | A+B+C | 17 | B | 25 | B+D |
| 2 | A+B | 10 | A | 18 | A | 26 | B |
| 3 | B (4) | 11 | D | 19 | C | 27 | C |
| 4 | B | 12 | C | 20 | C (10000) | 28 | A+B+C |
| 5 | A | 13 | A | 21 | B+C | 29 | B |
| 6 | B | 14 | B ([6]) | 22 | D | 30 | D |
| 7 | B | 15 | D (7) | 23 | B | 31 | C |
| 8 | A | 16 | C | 24 | A | 32 | D |

Two questions have overlapping options and are discussed in full in their solutions:
**Q22** (D vs B) and **Q32** (D vs B).

## Accuracy

Every JavaScript snippet in the paper was **executed in Node.js v22** while writing this guide.
The outputs printed in the document are real program output, not recalled from memory:

| Question | Verified output |
|---|---|
| Q1 | `Result: 80` / `Result: 120` / `80` / `function` |
| Q3 | `4` |
| Q13 | `END` / `A 1` / `B 2` / `C err` / `D 10` |
| Q14 | `[ 6 ]` |
| Q15 | `7` |
| Q19 | `HELLO WORLD` |
| Q20 | `10000` |
| Q24 | `true` `true` `true` `true` |

## Rebuilding the PDF

The PDF is produced from `solution.html` with headless Chromium. The stylesheet targets A4 with
`@page` rules, so no extra tooling is needed:

```bash
chrome --headless --no-sandbox --disable-gpu --no-pdf-header-footer \
       --print-to-pdf=WebDev_PYQ_Complete_Guide.pdf solution.html
```

Fonts used: **Noto Sans** for body text and **Source Code Pro** for code. Both are embedded in
the PDF, so it renders identically anywhere.
