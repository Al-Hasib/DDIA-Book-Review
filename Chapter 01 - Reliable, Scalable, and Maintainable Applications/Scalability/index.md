# Scalability

> "It is meaningless to say 'X is scalable' or 'Y doesn't scale.' Rather, discussing scalability means considering questions like 'If the system grows in a particular way, what are our options for coping with the growth?' and 'How can we add computing resources to handle the additional load?'"

## Overview

Even if a system works reliably today, that doesn't mean it will work reliably in the future. A common reason for degradation is **increased load**—more concurrent users, larger data volumes.

**Scalability** is the term we use to describe a system's ability to cope with increased load.

## What You'll Learn

1. How to describe load with load parameters
2. How to describe performance (throughput, latency, percentiles)
3. Common pitfalls with percentiles (tail latencies)
4. Approaches for coping with load

## Describing Load

Before discussing growth, we must **succinctly describe the current load**. Load can be described with a few numbers called **load parameters**. The best choice depends on your architecture:

- **Requests per second** to a web server
- The **ratio of reads to writes** in a database
- The number of **simultaneously active users** in a chat room
- The **hit rate** on a cache

### The Twitter Example

Using data published in November 2012, Twitter's two main operations:

| Operation | Load |
|-----------|------|
| **Post tweet** | 4.6k requests/sec avg, over 12k/sec at peak |
| **Home timeline** | 300k requests/sec |

Handling 12k writes/sec would be easy. The real challenge isn't tweet volume—it's **fan-out**: each user follows many people and is followed by many people. There are two ways to implement these operations:

**Approach 1 — On read:** Post inserts the tweet into a global collection. On read, look up all followed people, find their tweets, and merge them (a JOIN query).

**Approach 2 — On write (fan-out to cache):** Maintain a per-user home timeline cache (a "mailbox"). On post, look up followers and insert the tweet into each follower's cache. Reads become cheap because results are precomputed.

Twitter originally used approach 1 but switched to approach 2 because **write rate is almost two orders of magnitude lower than read rate**—it's preferable to do more work at write time and less at read time.

**The downside:** Posting now requires lots of extra work. Average tweet is delivered to ~75 followers → 4.6k tweets/sec becomes **345k writes/sec** to caches. And some users have **over 30 million followers**—a single tweet can cause over 30 million cache writes! Twitter tries to deliver within five seconds.

**Key load parameter:** the distribution of **followers per user** (weighted by tweet frequency), which determines fan-out load.

**The final twist — a hybrid:** Most users' tweets are fanned out at post time, but celebrities (huge follower counts) are excepted. Their tweets are fetched separately and merged at read time. This hybrid delivers consistently good performance (revisited in Chapter 12).

## Describing Performance

Once load is described, investigate what happens when load increases:

- Keep resources fixed, increase load → **how is performance affected?**
- Increase load, keep performance fixed → **how much must resources increase?**

### Throughput vs. Response Time

- **Throughput** — number of records processed per second (batch systems like Hadoop care about this)
- **Response time** — the time between a client sending a request and receiving a response (what matters in online systems)

**Latency vs. response time** (often confused, not the same):
- **Response time** is what the client sees: service time + network delays + queueing delays
- **Latency** is the duration a request is *waiting* to be handled—during which it is latent, awaiting service

### Response Times Are a Distribution

Even the same request repeated yields slightly different response times each time. Response time must be thought of as a **distribution of values**, not a single number. Variation comes from many causes: context switches, network packet loss + retransmission, garbage collection pauses, page faults, even mechanical vibrations in the server rack.

### Percentiles

The **mean (average)** isn't a good metric for "typical" response time because it doesn't tell you how many users actually experienced that delay. Better to use **percentiles**:

- **Median (p50)** — halfway point: half of requests are faster, half slower. Good for "how long do users typically wait."
- **p95, p99, p999** — the thresholds at which 95%, 99%, 99.9% of requests are faster. Used to understand outliers.

### Why High Percentiles (Tail Latencies) Matter

High percentiles directly affect the user experience. Amazon specifies internal service requirements at the **99.9th percentile** (1 in 1,000 requests) because the customers with the slowest requests often have the most data (i.e., the most valuable customers).

Business impact:
- Amazon: a **100 ms increase in response time reduces sales by 1%**
- Others: a **1-second slowdown reduces customer satisfaction by 16%**

But optimizing the 99.99th percentile was deemed too expensive with diminishing returns—it's easily affected by random events outside your control.

### SLOs and SLAs

Percentiles are often used in **service level objectives (SLOs)** and **service level agreements (SLAs)**. An SLA might state the service is "up" if it has a median under 200 ms and a 99th percentile under 1 s, and up at least 99.9% of the time.

### Head-of-Line Blocking

**Queueing delays** account for a large part of response time at high percentiles. A server processes only a small number of things in parallel, so a few slow requests can hold up subsequent requests—an effect known as **head-of-line blocking**. This is why it's important to **measure response times on the client side**.

**Test caution:** When generating artificial load, the client must keep sending requests **independently of response time**. If it waits for each response before the next request, it artificially keeps queues shorter than in reality, skewing measurements.

### Percentiles in Practice: Tail Latency Amplification

High percentiles matter especially for backend services called **multiple times** to serve a single end-user request. Even with parallel calls, the end-user request waits for the **slowest** call. One slow call makes the whole request slow. Even if few backend calls are slow, the chance of a slow call rises with more backend calls per request—an effect known as **tail latency amplification**.

**Calculating percentiles efficiently:** Keep a rolling window of recent response times; recompute percentiles periodically. The naïve sort is often too slow, so use algorithms like **forward decay**, **t-digest**, or **HdrHistogram**. **Beware:** averaging percentiles is mathematically meaningless—aggregate by **adding histograms**.

## Approaches for Coping with Load

How do we maintain good performance when load parameters increase?

> An architecture appropriate for one level of load is unlikely to cope with 10 times that load. On a fast-growing service, expect to **rethink your architecture on every order of magnitude increase**.

### Scaling Up vs. Scaling Out

- **Scaling up (vertical)** — moving to a more powerful machine
- **Scaling out (horizontal)** — distributing load across multiple smaller machines (a **shared-nothing architecture**)

A single-machine system is often simpler, but high-end machines get very expensive. In reality, good architectures use a **pragmatic mixture**—e.g., several fairly powerful machines can be simpler and cheaper than many small VMs.

### Elastic vs. Manual Scaling

- **Elastic systems** — automatically add resources when load increases (useful for unpredictable load)
- **Manually scaled systems** — a human analyzes capacity and adds machines (simpler, fewer operational surprises)

### Stateful Systems Are Harder

Distributing **stateless** services is fairly straightforward, but taking **stateful** data systems from single-node to distributed introduces lots of complexity. Common wisdom was to keep a database on a single node (scale up) until scaling cost or high-availability needs forced distribution. As distributed tools improve, this may change—distributed data systems could become the default even for small workloads.

### There Is No Magic Scaling Sauce

Scalable architecture is **highly specific to the application**—there's no one-size-fits-all scalable architecture. The problem may be volume of reads, writes, data to store, data complexity, response time requirements, access patterns, or (usually) some mix.

Example: A system for **100,000 requests/sec, each 1 kB** looks very different from one for **3 requests/min, each 2 GB**—even with the same data throughput.

An architecture that scales well is built around **assumptions about which operations are common vs. rare** (the load parameters). If those assumptions are wrong, scaling effort is wasted or counterproductive. In an early-stage startup, it's usually more important to **iterate quickly on features** than to scale for hypothetical future load.

Still, scalable architectures are built from **general-purpose building blocks arranged in familiar patterns**—the subject of this book.

## Key Takeaways

1. **Scalability isn't a label** — it's about questions of coping with specific growth.
2. **Load parameters** (requests/sec, read:write ratio, fan-out) define your bottleneck.
3. The **Twitter fan-out** example shows write-time vs. read-time trade-offs, and their hybrid.
4. **Response time is a distribution** — use percentiles, not the mean.
5. **Tail latencies (p99, p999)** matter most and drive real business impact.
6. **Tail latency amplification** — one slow backend call slows the whole request.
7. No **magic scaling sauce** — scalable architecture is application-specific; but concepts like scale up/out, elastic/manual, and shared-nothing recur.

## Discussion Questions

1. How would you describe load for a ride-sharing app like Uber?
2. Why is tail latency important in large-scale systems?
3. What are the tradeoffs between vertical and horizontal scaling?
4. Why is the mean a poor metric for "typical" response time?
5. What is head-of-line blocking, and why does it matter at high percentiles?
6. Can you think of an application where the load parameters would change the architecture choice?

## Notes

```markdown
Write your notes here...
```

## Next

- [Maintainability](Maintainability/index.md) — Keeping systems healthy over time
- [Summary](Summary/index.md) — Key takeaways from Chapter 1
