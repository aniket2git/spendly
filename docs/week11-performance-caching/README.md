# Week 11 – Graded Assignment: Performance & Caching

Complete step-by-step solutions for the MAD-II Week 11 graded assignment, written from
absolute beginner level with 18 custom diagrams.

**Topics:** performance metrics · performance tools · caching levels · ETag & If-Match ·
Flask-Caching · cookies · DOM events · image sizing · CDN

## Files

| File | What it is |
|---|---|
| [`Week11_Performance_Caching_Solutions.pdf`](Week11_Performance_Caching_Solutions.pdf) | The book. 36 pages, 18 diagrams. **Start here.** |
| `solution.html` | Source used to generate the PDF (all diagrams are inline SVG) |

## Answer key

| Q | Topic | Answer | The one line that decides it |
|---|---|---|---|
| 1 | flask_caching decorators | **B, C** | `memoize` keys on arguments; `cached` keys on the request path. With no arguments they match |
| 2 | Caching levels | **A, C** | Browser caching exists, proxy caching exists too, and a hard refresh clears your own cache |
| 3 | Proxy vs browser cache | **D** | All three are true: proxies are shared, hard refresh can't reach them, browser cache is nearest |
| 4 | Performance criteria | **A, B** | Throughput-with-latency and scalability. A framework choice is not a measurement |
| 5 | Performance tools | **A, C** | GTmetrix and Lighthouse analyse pages. Postman tests APIs |
| 6 | Cookies | **A, C** | Cookie size costs bytes on every request, and `domain=example.com` reaches subdomains |
| 7 | DOM events | **B** | Editing a paragraph needs only the DOM, so use the earlier event |
| 8 | Image scaling | **B** | 200×200 is four times the pixels, plus resizing work. Worse, not better |
| 9 | ETag and If-Match | **A, B, C** | Response header, quoted ASCII string, and If-Match means "only if it matches" |
| 10 | CDN | **A, B, C** | Content Delivery Network, a network of servers, shortening client-to-resource distance |

The source screenshots showed *in-progress selections* ("Flag for review" / "Clear Selection"
visible), not graded results, so every answer was derived independently and cross-checked
against official documentation. **All ten selections were already correct** — nothing to change.

## The three subtle ones

**Q1 — the decorators are easy to reverse.** `@cache.cached()` builds its key from the
**request path** (`view/<request.path>`); the function's parameters are **not** in the key.
`@cache.memoize()` puts the **arguments** in the key. So using `@cached` on a parameterised
function is a real bug:

```python
@cache.cached(timeout=60)
def square(n):
    return n * n

square(2)   # miss -> 4   stored under the path-based key
square(5)   # HIT on the same key -> returns 4    WRONG
```

Anchor it with the word itself: *memoization* means caching a result **per set of arguments**.
And for a function with **no** parameters, the only difference between them disappears — which
is why option C is true.

**Q2 vs Q3 look contradictory but aren't.** Q2 C says a hard refresh clears **your browser's**
cache. Q3 B says a hard refresh may **still** get a cached response **from a proxy**. Two
different caches, two different owners — clearing yours does not empty theirs.

**Q6 — naming a domain *widens* a cookie's reach.** Most students assume `domain=example.com`
restricts the cookie. It does the opposite: the cookie now goes to `example.com` **and all its
subdomains**, including `static.example.com`. To confine a cookie to one host, **omit** the
attribute. That bracketed condition in the question is the whole question.

## Facts worth memorising

1. Performance is **numbers**: latency (a duration), throughput (a rate), scalability
   (do both hold up under load?). A framework name is not a number.
2. **Lighthouse** and **GTmetrix** measure pages; **Postman** tests APIs.
3. Caches live at **browser**, **proxy**, **CDN edge** and **server** level — and
   **browser level has the least latency** because there is no network journey at all.
4. **ETag + If-None-Match** gets you a body-free **304 Not Modified**.
   **If-Match** means "only if it matches" and fails with **412 Precondition Failed**.
5. **`memoize` keys on arguments, `cached` keys on the path**; with no arguments they are the same.
6. Small cookies, correctly sized images, **`DOMContentLoaded`** over **`load`**, and a
   **CDN** to shorten the distance.

## Latency ladder

| Cache level | Shared? | Latency | Can a hard refresh clear it? |
|---|---|---|---|
| Browser | private, one user | **lowest** — no network at all | **yes** |
| Proxy | shared, many users | low | **no** |
| CDN edge | shared, geographic | low | no |
| Server-side (Flask-Caching) | shared | highest — full network trip | no |

## What's inside the PDF

- **Part 1** — latency vs throughput vs scalability, and why a framework choice isn't a metric
- **Part 2** — Lighthouse and GTmetrix, plus an honest note on what Postman can and can't do
- **Part 3** — the cache ladder, private vs shared caches, and what a hard refresh really reaches
- **Part 4** — the ETag round trip drawn out, and If-Match vs If-None-Match as opposites
- **Part 5** — `@cached` vs `@memoize`, the parameter-collision bug, and the no-argument case
- **Part 6** — cookie overhead maths and the `domain` attribute's subdomain behaviour
- **Part 7** — a second-by-second `DOMContentLoaded` vs `load` timeline
- **Part 8** — why scaling images in HTML costs 4× the pixel data
- **Part 9** — CDN edge servers and the distance argument
- **Part 10** — answer key, cheat sheet, a keyword radar, 8 practice questions with worked
  answers, and a 30-term glossary

## Sources

Technical facts were checked against
[the Flask-Caching documentation](https://flask-caching.readthedocs.io/) for `@cached`
(default key `view/request.path`) and `@memoize` (arguments included in the key);
[MDN on If-Match](https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Headers/If-Match)
and [MDN on If-None-Match](https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Headers/If-None-Match),
which confirm that for GET and HEAD the resource is returned only when the If-Match ETag
matches and that a mismatch yields 412; and MDN on
[DOMContentLoaded](https://developer.mozilla.org/en-US/docs/Web/API/Document/DOMContentLoaded_event),
[HTTP caching](https://developer.mozilla.org/en-US/docs/Web/HTTP/Guides/Caching) and
[cookies](https://developer.mozilla.org/en-US/docs/Web/HTTP/Guides/Cookies).
All explanations, analogies and diagrams were written and drawn for this document.
Content was rephrased for compliance with licensing restrictions.
