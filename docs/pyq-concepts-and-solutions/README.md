# MAD-II Previous Year Questions — Concepts from Zero, then Every Answer

A **95-page, 36-diagram** concept-first guide to a previous-year MAD-II paper. **32 questions**
covering JavaScript, Vue, Vuex, Vue Router, Flask, JWT, GraphQL, WebSockets and Git.

Every concept is taught **from zero before** its question appears, so you can read straight through
and already have the tool in hand by the time you reach each question.

## Files

| File | What it is |
|---|---|
| [`MAD2_PYQ_Concepts_and_Solutions.pdf`](MAD2_PYQ_Concepts_and_Solutions.pdf) | The book. 95 pages, 36 diagrams. **Start here.** |
| `solution.html` | Source used to generate the PDF (all diagrams are inline SVG) |

## How the answers were verified

- **All 8 pure-JavaScript output questions were executed in Node.js** (Q2, Q7, Q10, Q11, Q12, Q14,
  Q20, Q21) and the real console output is reproduced in the book. Those answers are not opinions.
- Framework behaviour was reasoned from documented behaviour and cross-checked against the option
  lists.
- Where a question is **ambiguously worded** (Q17), this is stated openly and both readings are
  explained rather than pretending the paper is perfect.

## Answer key

| Q | Topic | Answer |
|---|---|---|
| 1 | JS `this` keyword | Arrow functions have no own `this`, inherit from surrounding scope |
| 2 | Array `reduce` | **6** *[run]* |
| 3 | JWT vs sessions | Stateless — eliminates server-side session storage |
| 4 | WebSocket handshake | **GET** |
| 5 | ES module import | `import { strikeRate, playerName } from "./battingStats.js";` |
| 6 | JWT payload | User-related data (claims) — identity and expiration |
| 7 | Promise settles once | **Success!** *[run]* |
| 8 | Vuex async action | `['Angular', 'Vue', 'React']` |
| 9 | Vue Router wildcard | Redirects to /about and displays "About" |
| 10 | typeof / NaN / equality | **number, object, false, false** *[run]* |
| 11 | Classes and prototypes | Dog Labrador barks / This is a Dog / true / true / true *[run]* |
| 12 | Destructuring and rest | John / `{lastName, age}` / `{firstName, location, lastName, age}` *[run]* |
| 13 | Flask-Caching memoize | **10 seconds** |
| 14 | Promise reject + await | **Failed [75,75,63]** *[run]* |
| 15 | Vue directives match | **1-B, 2-D, 3-C, 4-A** |
| 16 | SPA client-side routing | Reduced backend load **+** seamless transitions |
| 17 | Cookies and performance | Size can impact performance **+** subdomain receives the cookie |
| 18 | Vue lifecycle hooks | Initial › Mounted › Ready › Done, **Value: 9** |
| 19 | Flask-Security roles | **200, 401, 403** |
| 20 | Shallow vs deep copy | **Ambrane 50 50 30** *[run]* |
| 21 | Arrow `this` capture | **100 undefined undefined** *[run]* |
| 22 | Flask threaded timing | **20, 40** |
| 23 | Vuex in a component | `this.$store.state.packed` and `this.$store.commit("ADD_ITEM", item)` |
| 24 | GraphQL | Mutations change the store **+** types, fields and per-field functions |
| 25 | Flask-JWT-Extended | Valid token in Authorization header **+** no token gives unauthorized |
| 26 | Git commands | `checkout -b` · `add .` · `commit -m` · `push origin feature-branch` |
| 27 | Vue async render delay | Parent already rendered **+** waits for response **+** async fetch after created |
| 28 | Computed run count | **1** |
| 29 | Computed re-evaluation | Runs again because a dependency changed |
| 30 | Why computed | Cached based on their dependencies |
| 31 | Router component reuse | Route changes, component reused, `updated()` called |
| 32 | Why `updated()` fires | Watched route param updates parent reactive state |

*[run]* = verified by executing the code.

## The five hardest questions, and the one fact each turns on

**Q18 (Vue lifecycle) — the expert's trap.** Hooks run `beforeCreate › created › beforeMount ›
mounted`, *not* the order written in the file. But the real trick is that **`beforeCreate` runs
before `data` exists**, so its changes are silently discarded. Apply all four hooks and you get
`Value: 14` — which is an offered option. Skip `beforeCreate` and you get **9**.

**Q14 (promise) — `reject` hidden after a satisfying loop.** The arithmetic gives `[75,75,63]` and
checks out (75+75+63 = 213). Then the last line is `reject(slots)`, not `resolve`. Answer is
**Failed [75,75,63]**. *Habit worth building: find the settle call before doing any arithmetic.*

**Q21 (`this`) — an arrow freezes `this` at creation.** `func1` works (100) because its arrow was
born inside `obj.outerFunc()` with the dot present. `func2()()` fails because the same arrow source
was born inside a bare, ownerless call. Same code, two frozen values.

**Q20 (shallow copy) — count the objects.** There are **3 outer objects but only 2 inner ones**.
`{...item}` copied the *address* of `stats`, so `item` and `ref2` share it. Answer:
**Ambrane 50 50 30**.

**Q31/Q32 (router) — reused, not recreated.** `/item/1` to `/item/2` matches the same
`/item/:id` pattern, so the component is **reused**: `created`/`mounted` do *not* re-run, but
`updated` does. This is the number one cause of a real Vue bug — fetching in `created` and wondering
why the page never refreshes. The fix is a watcher.

## Trap patterns

Part E1 of the PDF is a **Trap Museum** listing all 32 traps. They reduce to six patterns:

1. **The reversed pair** — two options say opposite things; exactly one is true
2. **The almost-right answer** — correct on 4 of 5 lines, wrong on one detail
3. **True but not the answer** — a correct sentence that does not answer what was asked (Q3: "JWTs
   are longer" is true, but it is a *disadvantage*)
4. **The absolute word** — *always, only, never, all* almost always signals false
5. **The distracting detail** — an unused parameter, a huge loop, hooks written out of order
6. **The self-contradiction** — two options cannot both be true, so one is free information

## What's inside

- **Part A** — JavaScript core: types and equality, references and copying, destructuring and
  spread, functions and `this`, classes and prototypes, `reduce`, promises and async/await, ES
  modules
- **Part B** — Vue: directives, lifecycle, computed vs methods, Vue Router, Vuex, SPA rendering
- **Part C** — Flask: request threading, Flask-Caching, JWT, Flask-Security roles, GraphQL
- **Part D** — platform: WebSocket handshake, cookies, Git workflow
- **Part E** — Trap Museum, six cheat sheets, 12 practice questions with worked answers

## Sources

Verified by execution in Node.js for all JavaScript output questions. Framework behaviour checked
against [Vue 2](https://v2.vuejs.org/), [Vuex](https://vuex.vuejs.org/),
[Flask](https://flask.palletsprojects.com/),
[Flask-Caching](https://flask-caching.readthedocs.io/),
[RFC 7519 (JWT)](https://datatracker.ietf.org/doc/html/rfc7519),
[RFC 6455 (WebSocket)](https://datatracker.ietf.org/doc/html/rfc6455),
[RFC 6265 (cookies)](https://datatracker.ietf.org/doc/html/rfc6265),
[MDN](https://developer.mozilla.org/), [graphql.org/learn](https://graphql.org/learn/) and
[git-scm.com/docs](https://git-scm.com/docs). All explanations, analogies, diagrams, worked traces
and practice questions were written and drawn for this document. Content was rephrased for
compliance with licensing restrictions.
