# DSSSB Section A — The Complete Book

The **common 100 marks** that every DSSSB post shares: General Awareness,
General Intelligence & Reasoning, Arithmetical & Numerical Ability, English,
and Hindi. One book that serves TGT (all subjects), PGT, PRT, LDC, DASS, JE,
ASO, Nursing Officer, Scientific Assistant and the rest.

## Download

| File | What it is |
|---|---|
| **`DSSSB_Section_A_Complete_Book.pdf`** | **The main book — 116 pages.** Start here. |
| `hindi_section_devanagari.html` | The Hindi part in **real Devanagari**. Open in a browser → Ctrl+P → "Save as PDF". |
| `hindi_section_devanagari.md` | Same Hindi content as plain UTF-8 Markdown. |
| `SECTION_A_printable.html` | Whole book as one HTML file — print to PDF from any browser. |
| `SECTION_A_full.md` | Whole book as one Markdown file — good for phone reading and search. |
| `seca_printable/` | One HTML file per Part, plus `index.html`. |
| `seca_markdown/` | One Markdown file per Part. |
| `seca_content/` | The source files the PDF is generated from. |

GitHub will not preview the PDF inline — use the **Download raw file** button
on the file page, or clone the repo.

## What is inside

| Part | Topic | Marks it targets |
|---|---|---|
| 1 | The Section A pattern and your strategy | — |
| 2 | General Awareness — Static GK | ~15 of 20 |
| 3 | General Awareness — Current Affairs | ~5 of 20 |
| 4 | Arithmetical and Numerical Ability | 20 |
| 5 | General Intelligence and Reasoning Ability | 20 |
| 6 | Test of English Language and Comprehension | 20 |
| 7 | Test of Hindi Language and Comprehension | 20 |
| 8 | Final revision and exam strategy | — |

156 worked practice questions with full explanations, plus per-topic
question-count estimates so you know where the marks actually sit.

## The pattern, and how it was verified

Section A is **5 sections × 20 questions = 100 marks**. The full paper is 200
marks in 2 hours, marked **+1 correct / −0.25 wrong**.

This was checked against **official DSSSB question booklets published on
dsssb.delhi.gov.in**, which print the section table and the per-question
marking on the cover page — not against coaching blogs. The exact source URLs
are cited inline in Chapter 1.1 of the book, along with the secondary sources
used for topic breakdowns. Content from all sources was paraphrased and
condensed for compliance with licensing restrictions.

**Still read your own notification.** Some posts are two-tier, and sectional
qualifying marks sometimes apply. The 20+20+20+20+20 shape of Section A has
been very stable; the wrapper around it varies by post.

## Two honest warnings

**1. Current affairs.** Part 3 gives you a *framework* — the recurring slots
DSSSB fills every year (sports events, appointments, awards, schemes, summits,
obituaries, defence, space), a blank slot table to fill in yourself, and a
daily routine. It deliberately does **not** print specific names and facts.
Any such list would be unverifiable against primary sources by the time you
read it, and wrong current-affairs facts cost you marks at −0.25 each. No book
can supply current affairs. You need a daily source for the 10–12 months
before your exam. The book tells you exactly what to look for.

**2. What score this book can realistically get you.** Reasoning + Maths +
English + Hindi are 80 marks and are almost entirely rule-based and
repetitive — **74–78 of those 80 is genuinely achievable** from this book
alone, with practice. General Awareness is the constraint: static GK is
covered thoroughly, but without a daily current-affairs habit you should
expect around **15 of 20** there. That puts the realistic ceiling from this
book at roughly **90**. Getting past 90 requires the daily habit described in
Part 3 — the book cannot do that part for you.

## Why Hindi is a separate file

The PDF is produced by a from-scratch PDF generator (no third-party libraries
were installable in the build environment). It draws WinAnsi glyphs only, and
there was no Devanagari font available on disk. Devanagari also needs complex
script shaping — matra reordering and conjunct formation — which cannot be
done reliably by hand.

So the Hindi part ships as UTF-8 Markdown and HTML, and your **browser** does
the shaping. Open `hindi_section_devanagari.html`, press **Ctrl+P**, choose
**Save as PDF**. You get correct Devanagari. Part 7 of the main PDF covers the
Hindi syllabus, strategy and question types in English/transliteration and
points to this file for the Devanagari detail.

## Building it yourself

Pure Python 3, no dependencies.

```
python3 seca.py           # -> DSSSB_Section_A_Complete_Book.pdf
python3 seca_formats.py   # -> SECTION_A_full.md, SECTION_A_printable.html, seca_*/
python3 hindi_html.py     # -> hindi_section_devanagari.{md,html}
```

## Companion books

- `dsssb-tgt-computer-science/` — 289-page Computer Science study book with all
  three DSSSB TGT CS previous-year papers fully solved.
- `question-bank/` — 583 labelled questions (`[PYQ]` / `[EXPECTED]`) with
  detailed explanations and topic weightage.
