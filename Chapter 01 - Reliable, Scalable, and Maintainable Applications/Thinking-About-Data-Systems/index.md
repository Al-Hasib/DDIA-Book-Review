# Thinking About Data Systems

> "The Internet was done so well that most people think of it as a natural resource like the Pacific Ocean, rather than something that was man-made."
> — Alan Kay

## Overview

Many applications today are **data-intensive**, as opposed to compute-intensive. Raw CPU power is rarely the limiting factor. The bigger problems are usually:

- The **amount** of data
- The **complexity** of data
- The **speed** at which data changes

## What You'll Learn

1. Why we group different tools under the umbrella term "data systems"
2. The standard building blocks of a data-intensive application
3. Why a single tool is often not enough
4. The three concerns: Reliability, Scalability, Maintainability

## The Standard Building Blocks

A data-intensive application is typically built from standard building blocks that provide commonly needed functionality:

1. **Databases** — Store data so that it can be found again later
2. **Caches** — Remember the result of an expensive operation to speed up reads
3. **Search indexes** — Search data by keyword or filter it in various ways
4. **Stream processing** — Send a message to another process, handled asynchronously
5. **Batch processing** — Periodically crunch a large amount of accumulated data

### Why This Seems Obvious

These data systems are such a **successful abstraction** that we use them all the time without thinking. Most engineers wouldn't dream of writing a new storage engine from scratch—databases are a perfectly good tool for the job.

## Beyond Databases

We typically think of databases, queues, caches, etc. as very different categories of tools. Although a database and a message queue both store data for a while, they have:

- Very different **access patterns**
- Different **performance characteristics**
- Very different **implementations**

### Why the Boundaries Are Blurring

New tools no longer fit neatly into traditional categories:

- **Datastores used as message queues** (e.g., Redis)
- **Message queues with database-like durability** (e.g., Apache Kafka)

The boundaries between categories are **becoming blurred**.

## The Composite Data System

Increasingly, applications have such demanding or wide-ranging requirements that a **single tool cannot meet all** of its data processing and storage needs. Instead:

1. The work is broken down into tasks that can be performed efficiently on a single tool.
2. Those different tools are **stitched together using application code**.

### Example Architecture

```
Application Code
      ↓
  [Cache] ←→ [Database] ←→ [Search Index]
      ↓
[Message Queue] → [Batch Processing]
```

If you have an application-managed caching layer (Memcached) or a full-text search server (Elasticsearch/Solr) separate from your main database, it's normally the **application code's responsibility** to keep those caches and indexes in sync with the main database.

### You Are a Data System Designer

When you combine several tools to provide a service, the service's **API** usually hides implementation details from clients. Now you've created a new, special-purpose data system from smaller, general-purpose components. Your composite data system may provide guarantees—e.g., that the cache is correctly invalidated on writes so outside clients see consistent results.

> **You are now not only an application developer, but also a data system designer.**

## Tricky Questions for System Designers

When designing a data system or service, many tricky questions arise:

1. How do you ensure data remains **correct and complete** even when things go wrong internally?
2. How do you provide **consistently good performance** even when parts of the system are degraded?
3. How do you **scale** to handle an increase in load?
4. What does a **good API** for the service look like?

Other factors influence design too: skills and experience of the people involved, legacy dependencies, delivery timescale, risk tolerance, regulatory constraints—these depend very much on the situation.

## The Three Concerns

This book focuses on three concerns important in most software systems:

1. **Reliability** — The system should continue to work correctly (performing the correct function at the desired level of performance) even in the face of adversity (hardware or software faults, and even human error).
2. **Scalability** — As the system grows (in data volume, traffic volume, or complexity), there should be reasonable ways of dealing with that growth.
3. **Maintainability** — Over time, many different people will work on the system (engineering and operations), maintaining current behavior and adapting to new use cases, and they should all be able to work on it productively.

These words are often cast around without a clear understanding of what they mean. The rest of this chapter explores ways of thinking about them—then later chapters look at the techniques, architectures, and algorithms used to achieve those goals.

## Key Takeaways

1. Data-intensive means data is the challenge: **quantity, complexity, or speed of change**.
2. Standard building blocks: **databases, caches, search indexes, stream processing, batch processing**.
3. Categories are blurring, and **one tool rarely does it all** — you combine tools with application code.
4. Combining tools makes you a **data system designer**, not just an app developer.
5. The three foundational concerns: **Reliability, Scalability, Maintainability**.

## Discussion Questions

1. What other components might be part of a data system?
2. How do these components interact with each other?
3. Why is it important to think about the whole system, not just the database?
4. Can you think of an example where a single tool couldn't meet all your needs, and you had to combine tools?
5. How does the API hide implementation details in a composite data system?
6. What does it mean to be a "data system designer" rather than just an application developer?

## Notes

```markdown
Write your notes here...
```

## Next

- [Reliability](Reliability/index.md) — Working correctly even when things go wrong
- [Scalability](Scalability/index.md) — Handling increased load
- [Maintainability](Maintainability/index.md) — Keeping systems healthy over time
