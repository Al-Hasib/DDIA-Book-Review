# Teaching Script: Introduction to DDIA (15–20 Minutes)

> **Target time:** 15–20 minutes
> **Audience:** Software engineers/students with basic database & web knowledge
> **Goal:** Set the stage — what this book is about, why it matters, and how it's organized

---

## Segment 1: Hook — The Buzzword Problem (3 min)

**Say:**
> "Raise your hand if you've heard these words thrown around at work or in job postings: NoSQL, Big Data, Web-scale, Sharding, Eventual consistency, ACID, CAP theorem, MapReduce, Real-time. That's a lot of buzzwords. And honestly, they signal real enthusiasm for new technology. But here's the problem: enthusiasm alone doesn't make you a good engineer."

**Ask:**
> "Have you ever used a buzzword without being able to explain *why* the technology exists or when you'd actually choose it over something else?"

**Key point to land:**
> "This book's whole premise is that we need to dig deeper than buzzwords and understand the *enduring principles* underneath. If you understand the principles, every new tool just becomes another example of the same ideas."

---

## Segment 2: Why Is This Happening? Driving Forces (3 min)

**Say:**
> "So why is all this change happening? There are a few big forces pushing it forward."

Use a **whiteboard** and list:

1. **Huge internet companies** (Google, Amazon, Facebook) handle massive data and traffic → build new tools to scale.
2. **Business agility** — companies want to test ideas cheaply and iterate fast with flexible data models.
3. **Open source software** is now preferred and very successful.
4. **Hardware** — CPU speeds have plateaued, but we have multi-core processors and faster networks → more parallelism.
5. **Cloud/IaaS (AWS)** — even small teams can build distributed systems across the world.
6. **Availability expectations** — downtime is increasingly unacceptable.

**Say:**
> "Now here's a key distinction the author makes: when we say an application is *data-intensive*, we mean data is the real challenge — the *quantity*, the *complexity*, or the *speed* it changes. That's different from *compute-intensive*, where CPU cycles are the bottleneck."

**Practical check-in:**
> "Think of something you've worked on. Was data the hard part, or was it CPU power? Most modern apps are data-intensive."

---

## Segment 3: The Enduring Principles (2 min)

**Say:**
> "The thing that makes this book worth reading is this idea: behind all the rapid tech changes are *enduring principles* that stay true no matter which version of a tool you use. The buzzwords change every few years, but the underlying ideas don't."

**Write on board:**
> Principles → Where each tool fits → How to use it → How to avoid its pitfalls

**Say:**
> "This book is not a tutorial for one tool, and it's not dry theory. It's about *why* systems work the way they do — the key algorithms, the trade-offs, the questions you should ask."

---

## Segment 4: Who Is This For? (2 min)

**Say:**
> "Who is this book for? Honestly, if you build any app with a backend that stores or processes data — a web app, a mobile app, a sensor network — this book is for you. It's written for engineers, architects, and technical managers who like to code, especially anyone making architecture decisions."

**Expected background:**
- Some experience building web apps or network services
- Familiar with relational databases and SQL
- TCP/HTTP understanding is helpful, not required
- Language/framework doesn't matter

**Address the common objection:**
> "A lot of people say: 'You're not Google or Amazon. Stop worrying about scale and just use a relational database.' There's some truth there — building for scale you don't need is premature optimization. But you still need to choose the *right tool for the job*. Relational databases are important, but they're not the final word."

---

## Segment 5: The Three Parts — The Map (4 min)

**Say:**
> "Here's the roadmap. The book is divided into three parts, and this is the mental map you should walk away with today."

Draw a diagram with **three boxes**:

**Part I — Foundations of Data Systems (Ch 1–4)**
- Ch 1: Reliability, Scalability, Maintainability *(the big three)*
- Ch 2: Data Models & Query Languages
- Ch 3: Storage Engines (how data is arranged on disk)
- Ch 4: Encoding & Schema Evolution

**Part II — Distributed Data (Ch 5–9)**
- Ch 5: Replication
- Ch 6: Partitioning / Sharding
- Ch 7: Transactions
- Ch 8: The Trouble with Distributed Systems
- Ch 9: Consistency & Consensus

**Part III — Derived Data (Ch 10–12)**
- Ch 10: Batch Processing
- Ch 11: Stream Processing
- Ch 12: The Future — putting it all together

**Say:**
> "Part I is about one machine. Part II is what happens when data spans many machines — and that's where a lot of the real hard problems live. Part III is about systems that *derive* one set of data from another."

---

## Segment 6: Wrap Up & Call to Action (2–3 min)

**Summarize the key takeaways:**
1. Data is the primary challenge in modern apps — quantity, complexity, or speed of change.
2. Behind the buzzwords are **enduring principles**.
3. This book teaches you to **navigate and reason about** the landscape, not just memorize tools.
4. The foundation is **reliability, scalability, and maintainability** — coming up in Chapter 1.

**Bridge to next session:**
> "Next session, we start Part I with the most important chapter: 'Reliable, Scalable, and Maintainable Applications.' We'll define what those three words actually mean and how you can achieve them. That's the foundation everything else builds on."

**Close with a discussion question:**
> "Before we go — think about the last system you built or used. Was it reliable, scalable, and maintainable? Which of the three was hardest to achieve? We'll dig into exactly that next time."

---

## Segment Time Budget (Total ~18 min)

| Segment | Time |
|---------|------|
| 1. Hook — Buzzword Problem | 3 min |
| 2. Driving Forces | 3 min |
| 3. Enduring Principles | 2 min |
| 4. Who Is This For | 2 min |
| 5. The Three Parts Map | 4 min |
| 6. Wrap Up & Next Steps | 2–3 min |
| **Total** | **~16–18 min** |

---

## Suggested Whiteboard / Slide Layout

```
WHY NOW?                    THE MAP (3 Parts)
1. Internet giants          ┌───────────────────────────┐
2. Business agility         │ PART I: Foundations (1-4) │
3. Open source              │  one machine              │
4. Hardware / parallelism   ├───────────────────────────┤
5. Cloud / IaaS             │ PART II: Distributed (5-9)│
6. Availability             │  many machines            │
                            ├───────────────────────────┤
DATA-INTENSIVE vs           │ PART III: Derived (10-12)│
COMPUTE-INTENSIVE           └───────────────────────────┘

CORE IDEA:
Enduring principles behind the buzzwords
```

---

## References

- [Introduction notes](introduction.md)
- Martin Kleppmann, *Designing Data-Intensive Applications* (Preface), O'Reilly Media
