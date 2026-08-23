# Graded Assignment: Webhooks, Polling, SSE, WebSockets & Pub/Sub

Complete step-by-step solutions for the MAD-II graded assignment on inter-application
communication, written from absolute beginner level with 19 custom diagrams.

**Topics:** Webhooks · short polling · long polling · Server-Sent Events · WebSockets ·
pub/sub messaging · message brokers

## Files

| File | What it is |
|---|---|
| [`Webhooks_Polling_SSE_PubSub_Solutions.pdf`](Webhooks_Polling_SSE_PubSub_Solutions.pdf) | The book. 37 pages, 19 diagrams. **Start here.** |
| `solution.html` | Source used to generate the PDF (all diagrams are inline SVG) |

## Answer key

| Q | Topic | Answer | The one line that decides it |
|---|---|---|---|
| 1 | Webhooks, general | **A, D** | Respond immediately; a trivial Flask app is enough. Both wrong options say "cannot" |
| 2 | Webhooks vs WebSockets | **A, B, C** | Webhook = HTTP, server-to-server. WebSocket = 2-way. Only WebSockets stay open |
| 3 | Polling and long poll | **A, C** | Polling repeats at fixed intervals and needs no persistent connection |
| 4 | SSE (pick the false one) | **B** | SSE needs an open HTTP stream and a listener — never a task queue |
| 5 | Short polling | **A, C** | Immediate reply every time, even an empty one, at a fixed interval |
| 6 | Long polling | **B** | No data means no reply yet; the connection is held open |
| 7 | Webhook vs API | **A, D** | Webhooks push and are **asynchronous**; an API can pull and push. **Not C** |
| 8 | Pub/Sub | **A, B, D** | Enables event-driven architecture, delivers to subscribers at once, asynchronous |
| 9 | Message broker | **A, D** | Correct routing and fan-out. Brokers *do* retry, and they are FIFO not LIFO |
| 10 | Webhooks, details | **A, D** | Content in the request body; one-way. Response stays small; no humans involved |

## The one correction

The screenshots this was written from showed *in-progress selections* (with "Flag for
review" and "Clear Selection" visible), not graded results. Every answer above was derived
independently and cross-checked against official documentation.

Nine of the ten selections were already correct. **Question 7 needs option C unticked.**

> **C. Webhooks are generally synchronous in nature.** — This is **false**.

Webhooks are **asynchronous** and **event-driven**: the receiver never asks for the data
and never waits for it, it simply reacts when an event happens to arrive. *Synchronous*
describes the **API** model, where the caller sends a request and blocks until the reply
comes back.

There is a grain of truth that traps people: one individual webhook delivery is an HTTP
request that waits for a `200` response. But that is true of every HTTP call ever made — it
describes the transport, not the nature of the pattern. A useful consistency check: Q8 of
the same paper marks *"the communication is asynchronous in nature"* as **correct** for
pub/sub, and pub/sub is the same shape of thing (event happens, message pushed, receiver
reacts later).

## The five techniques at a glance

| | Short polling | Long polling | SSE | WebSocket | Webhook |
|---|---|---|---|---|---|
| **Who starts** | client | client | client opens it | client shakes hands | **server** |
| **Direction** | both, one at a time | both, one at a time | **one way** (server→client) | **two way** | **one way** |
| **Connection** | **closes** each time | **held open** until data | **stays open** | **stays open** | **closes** after the POST |
| **Protocol** | HTTP | HTTP | HTTP | `ws://` after upgrade | HTTP |
| **Wasted traffic** | **very high** | low | very low | very low | **none** |
| **Mainly between** | browser↔server | browser↔server | browser↔server | browser↔server | **server↔server** |
| **Sync/async** | synchronous | sync request, delayed reply | async stream | async both ways | **async, event-driven** |

## Six facts worth memorising

1. HTTP makes the **client speak first** — every technique here works around that.
2. **Short** polling answers instantly even with nothing; **long** polling holds the
   connection open and stays silent.
3. **SSE is one way** (a loudspeaker); a **WebSocket is two way** (a phone call).
4. A **webhook** is push, server-initiated, one way, **asynchronous**, server-to-server;
   it closes immediately and needs a fast `200`.
5. An **API can pull and push**; a **webhook only pushes**.
6. **Pub/Sub** fans one message out to every subscriber of a topic; a **broker** routes,
   retries, and works **FIFO** (not LIFO).

## What's inside the PDF

- **Part 1** — the one problem behind all 10 questions: HTTP is client-initiated
- **Part 2** — short polling, with a timeline showing the wasted requests and stale data
- **Part 3** — long polling, plus the "persistent connection" trap
- **Part 4** — Server-Sent Events, with working Flask + `EventSource` code and a
  myth-buster on what SSE does *not* need
- **Part 5** — WebSockets: the handshake and full duplex
- **Part 6** — webhooks: the end-to-end flow, why the receiver must answer immediately,
  how to secure a public URL, and API pull vs webhook push
- **Part 7** — pub/sub fan-out and the four jobs of a message broker
- **Part 8** — all five techniques in one comparison table, plus a decision tree
- **Part 9** — answer key, cheat sheet, a keyword radar for spotting *cannot / must /
  all of the above* traps, 8 practice questions with worked answers, and a 30-term glossary

## Sources

Technical facts were checked against
[MDN on Server-Sent Events and EventSource](https://developer.mozilla.org/en-US/docs/Web/API/Server-sent_events),
[MDN on the WebSockets API](https://developer.mozilla.org/en-US/docs/Web/API/WebSockets_API),
and [the Flask documentation](https://flask.palletsprojects.com/). The characterisation of
webhooks as push-based and event-driven, in contrast to the request-response pull model of
an API, was cross-checked across multiple independent technical references. Pub/Sub delivery
semantics were checked against broker documentation and messaging-pattern references. All
explanations, analogies and diagrams were written and drawn for this document. Content was
rephrased for compliance with licensing restrictions.
