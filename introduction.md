# Introduction: Designing Data-Intensive Applications (DDIA)

> "We have to dig deeper than buzzwords."

## Overview

Welcome to *Designing Data-Intensive Applications* by Martin Kleppmann. This introduction explains what the book is about, who it's for, and how it is organized. It sets the stage for the entire journey through reliability, scalability, maintainability, distributed systems, and derived data.

## The Problem: A World of Buzzwords

In recent years, software engineers—especially those working in server-side and backend systems—have been flooded with buzzwords:

- NoSQL! Big Data! Web-scale! Sharding!
- Eventual consistency! ACID! CAP theorem!
- Cloud services! MapReduce! Real-time!

These buzzwords signal genuine enthusiasm for new possibilities. **But enthusiasm alone isn't enough.** As software engineers and architects, we need a technically accurate and precise understanding of the technologies and their trade-offs. That means digging deeper than the buzzwords.

## Why Is This Happening? The Driving Forces

Several forces are driving these developments in databases, distributed systems, and the way we build applications on top of them:

1. **Massive internet companies** (Google, Yahoo!, Amazon, Facebook, LinkedIn, Microsoft, Twitter) handle huge volumes of data and traffic, forcing them to build new tools that scale efficiently.
2. **Business agility**—companies need to test hypotheses cheaply and respond quickly to market insights by keeping development cycles short and data models flexible.
3. **Free and open source software** has become very successful and is often preferred over commercial or bespoke in-house software.
4. **Hardware changes**—CPU clock speeds are barely increasing, but multi-core processors are standard and networks are getting faster. Parallelism is only increasing.
5. **Infrastructure as a service (IaaS)**—even small teams can build distributed systems across many machines and geographic regions (e.g., Amazon Web Services).
6. **High availability expectations**—extended downtime due to outages or maintenance is increasingly unacceptable.

## Data-Intensive vs. Compute-Intensive

An application is **data-intensive** if *data* is its primary challenge:

- The **quantity** of data
- The **complexity** of data
- The **speed** at which data changes

This is opposed to **compute-intensive**, where CPU cycles are the bottleneck.

While NoSQL databases get most of the attention, message queues, caches, search indexes, batch/stream processing frameworks, and related technologies are equally important. Most applications use a combination of these.

## The Enduring Principles

Behind the rapid changes in technology, there are **enduring principles** that remain true regardless of which version of a tool you use. If you understand these principles, you can:

- See where each tool fits in
- Make good use of each tool
- Avoid its pitfalls

## The Goal of This Book

> "We will look at examples of successful data systems... we will try to find useful ways of thinking about data systems—not just how they work, but also *why* they work that way."

This book is **not** a tutorial for one particular tool, nor a textbook of dry theory. Instead, it:

- Explores the internals of successful data systems
- Digs into key algorithms, principles, and trade-offs
- Examines *why* systems work the way they do
- Asks the questions we need to ask

**After reading it**, you'll be able to decide which kind of technology is appropriate for which purpose, and how tools combine to form a good application architecture. You won't build a database storage engine from scratch (that's rarely necessary), but you'll develop strong intuition for what your systems do under the hood—so you can reason about their behavior, make good design decisions, and track down problems.

## Who Should Read This Book?

This book is for you if you develop applications with a server/backend that stores or processes data and uses the internet (web apps, mobile apps, internet-connected sensors).

It's for **software engineers, architects, and technical managers who love to code**, especially those making architecture decisions.

**You should have:**
- Some experience building web apps or network services
- Familiarity with relational databases and SQL
- A general understanding of TCP and HTTP (helpful, not required)

**Language/framework choice doesn't matter.** Nonrelational database experience is a bonus, not required.

You'll find this book valuable if you:
- Want to make data systems **scalable** (e.g., support millions of users)
- Need **high availability** and operational robustness
- Want systems that are **easier to maintain** long-term
- Are **curious about how things work** inside major websites and services

### The "You're Not Google" Objection

People often say: *"You're not Google or Amazon. Stop worrying about scale and just use a relational database."*

There's truth here—building for scale you don't need is wasted effort and a form of premature optimization. **However**, it's also important to choose the *right tool for the job*. Different technologies have different strengths and weaknesses. Relational databases are important but not the final word.

## Scope of This Book

**What it covers:**
- Principles and trade-offs fundamental to data systems
- Design decisions taken by different products

**What it does NOT cover:**
- Detailed installation/usage instructions for specific software (there's plenty of existing documentation)
- Deployment, operations, security, and management (these deserve books of their own)

**Language note:** The term "Big Data" is overused and underdefined. The book uses clearer terms like *single-node vs. distributed systems* and *online/interactive vs. offline/batch processing*.

The book has a **bias toward free and open source software (FOSS)** because reading source code is a great way to understand how systems work, and open platforms reduce vendor lock-in. But it also discusses proprietary software where appropriate.

## Outline of the Book

The book is arranged into **three parts**:

### Part I: Foundations of Data Systems (Chapters 1–4)
Fundamental ideas that apply to all data systems:
- **Chapter 1** – Reliability, scalability, and maintainability—what we're trying to achieve
- **Chapter 2** – Data models and query languages, and how they fit different situations
- **Chapter 3** – Storage engines: how databases arrange data on disk
- **Chapter 4** – Data encoding (serialization) and schema evolution over time

### Part II: Distributed Data (Chapters 5–9)
Moving from one machine to data distributed across many:
- **Chapter 5** – Replication
- **Chapter 6** – Partitioning/sharding
- **Chapter 7** – Transactions
- **Chapter 8** – The problems with distributed systems
- **Chapter 9** – Consistency and consensus in distributed systems

### Part III: Derived Data (Chapters 10–12)
Systems that derive some datasets from others:
- **Chapter 10** – Batch processing
- **Chapter 11** – Stream processing
- **Chapter 12** – Bringing it together: building reliable, scalable, maintainable applications in the future

## Why This Matters

> "If you understand those principles, you're in a position to see where each tool fits in, how to make good use of it, and how to avoid its pitfalls."

Understanding data systems is crucial to building **reliable**, **scalable**, and **maintainable** systems—the foundation for everything in this book. The enduring principles give you durable knowledge that outlives any specific tool or version.

## Key Takeaways

1. Data-intensive applications treat **data as the primary challenge** (quantity, complexity, or speed of change).
2. Behind the buzzwords lie **enduring principles** that remain true across tool versions.
3. The book's goal is to help you **navigate and reason about** the fast-changing landscape of data technologies.
4. **Reliability, scalability, and maintainability** are the foundational concerns—detailed in Chapter 1.

## Practice Questions

1. What distinguishes a data-intensive application from a compute-intensive one?
2. List three driving forces behind the recent developments in data systems.
3. Why is it not enough to just memorize the buzzwords?
4. Who is this book written for, and what background is expected?
5. What are the three parts of the book, and what does each cover?
6. Why does the book prefer free and open source software, and where does it still discuss proprietary software?
7. What is the "You're not Google" objection, and how does the book respond to it?

## Next

Now that you understand what the book is about, continue to **[Part I: Foundations of Data Systems](Chapter%2001%20-%20Reliable%2C%20Scalable%2C%20and%20Maintainable%20Applications/index.md)** — starting with **Reliability, Scalability, and Maintainability**.
