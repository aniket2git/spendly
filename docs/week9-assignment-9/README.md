# Week 9 – Graded Assignment 9: Illustrated Solutions

Complete step-by-step solutions for **MAD-II Week 9 Graded Assignment 9**, written from
absolute beginner level with 21 custom diagrams.

**Topics:** Flask request threading and timing · Redis · Celery · concurrency vs
parallelism · message queues and message brokers

## Files

| File | What it is |
|---|---|
| [`Week9_Assignment9_Solutions.pdf`](Week9_Assignment9_Solutions.pdf) | The book. 41 pages, 21 diagrams. **Start here.** |
| `solution.html` | Source used to generate the PDF (all diagrams are inline SVG) |

## Answer key

| Q | Topic | Answer | The one line that decides it |
|---|---|---|---|
| 1 | Flask, default threading | **B** — 20, 40 | `app.run()` is threaded by default, so both requests start together |
| 2 | Flask, `threaded=False` | **A** — 20, 50 | One thread, so `/profile` waits 10 s first: 10 + 30 = 40 s after 10:10:10 |
| 3 | Redis basics | **A, D** | Always works in RAM; stores key-value pairs. Disk is only a backup |
| 4 | Redis features | **A, B, C** | Many data types, TTL expiry, authentication. TTL 1 means 1 second, not "never" |
| 5 | Celery | **A, B, D** | Multiple brokers, auto retry, Flower + Beat. "Only Redis and RabbitMQ" is false |
| 6 | Concurrency (pick the false one) | **C** | Multi-core concurrency does not *always* need context switching |
| 7 | Concurrency vs parallelism (false one) | **B** | Parallelism without concurrency is impossible |
| 8 | Message queue | **A, B, D** | It is a temporary buffer; in point-to-point a message is consumed once |
| 9 | Message broker, connections | **A, C** | n + m instead of n × m, and batch processing is possible. B has a stray "not" |
| 10 | Message broker, coupling | **A, C** | Sender need not know the receiver's state; communication is asynchronous |

## The Q1 vs Q2 trap

Questions 1 and 2 show the **same** `app.py` and `index.html`. Only the last line differs,
and that single word flips the answer:

| | Q1 — `app.run(debug=True)` | Q2 — `app.run(threaded=False, debug=True)` |
|---|---|---|
| Threads available | many (Flask's default) | exactly one |
| `/` finishes | 10:10:20 → logs **20** | 10:10:20 → logs **20** |
| `/profile` starts | t = 0, no waiting | t = 10, after queueing |
| `/profile` finishes | 10:10:40 → logs **40** | 10:10:50 → logs **50** |
| Console | **20, 40** (B) | **20, 50** (A) |

`app.run()` sets `threaded=True` for you from **Flask 1.0** onwards, so plain
`app.run(debug=True)` already serves requests simultaneously. `threaded=False` is a
downgrade you opt into, which forces the second request to queue for 10 seconds.

The reusable formula:

```
answer second = ( start second + time spent waiting + own sleep ) mod 60
```

Waiting time is 0 on a threaded server, and equals the total sleep of everything ahead of
you in the queue on a single-threaded one.

## Five facts worth memorising

1. Flask's `app.run()` is **threaded by default**; `threaded=False` makes it queue.
2. The clock is read **after** the sleep, so waiting time is part of the answer.
3. Redis works in RAM, stores key-value pairs, and **TTL `-1`** means "never expires"
   (`1` means one second left, `-2` means the key is gone).
4. **Parallel implies concurrent**, never the other way round.
5. A broker turns **n × m** connections into **n + m**, and lets senders fire and forget.

## What's inside the PDF

- **Parts 1–3** — foundations from zero: client/server and the request-response cycle,
  URL anatomy, Flask routes, `time.sleep`, `datetime.now().second`, and how JavaScript
  `fetch` and promises fire two requests in the same instant
- **Part 4** — Q1 and Q2 with second-by-second Gantt timelines
- **Part 5** — Redis: RAM vs disk speed, data types, the TTL countdown, persistence
- **Part 6** — Celery: producer → broker → worker → result backend, plus Flower and Beat
- **Part 7** — concurrency vs parallelism: context switching, true parallelism, Venn diagram
- **Part 8** — message queues and brokers: point-to-point vs pub/sub, the n×m vs n+m
  connection argument, synchronous vs asynchronous
- **Part 9** — answer key, cheat sheet, a "keyword radar" for spotting *always / only /
  never / not* traps, 7 practice questions with worked answers, and a 30-term glossary

## Sources

Technical facts come from the official documentation of
[Flask](https://flask.palletsprojects.com/), [Redis](https://redis.io/docs/) and
[Celery](https://docs.celeryq.dev/), plus the Week 9 course material. The detail that
Flask's `app.run()` defaults to `threaded=True` from Flask 1.0 was cross-checked against
[community documentation on Stack Overflow](https://stackoverflow.com/questions/14814201/).
All explanations, analogies and diagrams were written and drawn for this document.
Content was rephrased for compliance with licensing restrictions.
