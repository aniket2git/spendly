# DSSSB TGT Computer Science — Complete Study Material

Three books covering the **entire 200-mark paper**. All generated from source
in this branch; nothing here is a scanned or copied third-party book.

| # | Book | Pages | Covers | Folder |
|---|---|---|---|---|
| 1 | **Computer Science Study Book** | 289 | Section B — the full CS syllabus, basics to advanced, **all 3 DSSSB TGT CS previous-year papers fully solved** | [`dsssb-tgt-computer-science/`](dsssb-tgt-computer-science/) |
| 2 | **Section-wise Question Bank** | 137 | Section B — **583 questions** with detailed explanations and per-topic weightage | [`question-bank/`](question-bank/) |
| 3 | **Section A Complete Book** | 116 | Section A — GA, Reasoning, Maths, English, Hindi (the common 100 marks) | [`section-a/`](section-a/) |

## Direct PDF links

- [DSSSB_TGT_Computer_Science_Study_Book.pdf](dsssb-tgt-computer-science/DSSSB_TGT_Computer_Science_Study_Book.pdf)
- [DSSSB_KVS_NVS_TGT_CS_Question_Bank.pdf](question-bank/DSSSB_KVS_NVS_TGT_CS_Question_Bank.pdf)
- [DSSSB_Section_A_Complete_Book.pdf](section-a/DSSSB_Section_A_Complete_Book.pdf)
- [Hindi in Devanagari (HTML → Ctrl+P → Save as PDF)](section-a/hindi_section_devanagari.html)

GitHub shows *"binary file preview not supported"* for PDFs. Use the
**Download raw file** button on the file page, or `git clone` the branch.

## How the 200 marks break down

| | Component | Marks |
|---|---|---|
| **Section A** | General Awareness | 20 |
| | General Intelligence & Reasoning Ability | 20 |
| | Arithmetical & Numerical Ability | 20 |
| | Test of English Language & Comprehension | 20 |
| | Test of Hindi Language & Comprehension | 20 |
| **Section B** | Computer Science subject + teaching methodology | 100 |
| | **TOTAL** | **200** |

2 hours. **+1** correct, **−0.25** wrong, **0** skipped. CBT, four options.

Book 3 covers all of Section A. Books 1 and 2 cover Section B. Read Part 1 of
Book 3 first — it explains where the marks actually are.

## Suggested order

1. **Book 3, Part 1** — the pattern and a realistic marks plan. 30 minutes.
2. **Book 1** — the CS syllabus, in order. This is the longest haul.
3. **Book 3, Parts 4–7** — Reasoning, Maths, English, Hindi. Rule-based and
   repetitive; the fastest marks per hour of study in the whole paper.
4. **Book 2** — question bank, once the theory is in place. Use it to find
   gaps, not to learn from cold.
5. **Book 3, Parts 2–3** — Static GK throughout; current affairs daily for the
   10–12 months before the exam.
6. **Book 3, Part 8** — final revision and exam-day strategy.

## Two things stated plainly

**Current affairs cannot come from a book.** Book 3 Part 3 gives you the
recurring slots DSSSB fills every year, a blank table to fill in yourself, and
a daily routine — but not a list of names and facts. Such a list would be
unverifiable against primary sources and stale by the time you sat the exam,
and wrong GA answers cost −0.25 each.

**Realistic ceiling.** From these books alone, Reasoning + Maths + English +
Hindi (80 marks) will genuinely get you 74–78 with practice, and Section B is
covered thoroughly. General Awareness caps around 15/20 without a daily
current-affairs habit. That puts the honest ceiling at roughly **90 in Section
A**. Getting past that needs the daily habit — no book substitutes for it.

## Sources and verification

The exam pattern was verified against **official DSSSB question booklets
published on dsssb.delhi.gov.in**, which print the section table and
per-question marking on the cover page. Source URLs are cited inline in each
book. Secondary sources were consulted only for topic breakdowns, and their
content was paraphrased and condensed for compliance with licensing
restrictions.

In Book 1, **nine official answer keys are flagged `KEY NOTE`** where the
released key conflicts with standard textbook theory (e.g. the HTTP vs CGI
item, "bit stream" attributed to Data Link rather than Physical layer,
`stdio.h` vs `stdarg.h`, p-series convergence, and
`printf(6+"Hello World\n")`). Both the key's answer and the theory are
explained so you are not blindsided either way.

In Book 2, every question is labelled **`[PYQ]`** (284 — verified DSSSB
previous-year questions) or **`[EXPECTED]`** (299 — written to match the
syllabus and observed pattern). Nothing is presented as a real past paper
question unless it is one.

## Building from source

Pure Python 3, no third-party dependencies (none were installable in the build
environment, so the PDF generator is written from scratch).

```
python3 book.py            # Book 1
python3 qbank.py           # Book 2
python3 seca.py            # Book 3
python3 seca_formats.py    # Book 3 markdown + printable HTML
python3 hindi_html.py      # Devanagari Hindi files
```
