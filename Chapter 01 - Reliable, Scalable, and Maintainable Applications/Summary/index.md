# Summary

## Overview

This chapter explored fundamental ways of thinking about data-intensive applications. These principles guide us through the rest of the book, where we dive into deep technical detail. There's **no easy fix** for making applications reliable, scalable, or maintainable—but there are patterns and techniques that keep reappearing across different applications.

## Requirements of an Application

An application must meet various requirements to be useful:

- **Functional requirements** — what it should do (allowing data to be stored, retrieved, searched, and processed in various ways)
- **Nonfunctional requirements** — general properties like **security, reliability, compliance, scalability, compatibility, and maintainability**

This chapter discussed **reliability, scalability, and maintainability** in detail.

## The Three Concerns (Recap)

### Reliability

Making systems work correctly **even when faults occur**. Faults come in three types:

- **Hardware faults** — typically random and uncorrelated
- **Software faults** (bugs) — typically systematic and hard to deal with
- **Human faults** — humans inevitably make mistakes from time to time

**Fault-tolerance techniques** can hide certain types of faults from the end user.

### Scalability

Having strategies for keeping **performance good even when load increases**. To discuss it, we first need ways to describe load and performance quantitatively:

- **Describing load** — the Twitter home timeline example
- **Measuring performance** — response time percentiles

In a scalable system, you can **add processing capacity** to remain reliable under high load.

### Maintainability

Has many facets, but in essence it's about **making life better for the engineering and operations teams** who need to work with the system:

- **Good abstractions** help reduce complexity and make the system easier to modify and adapt for new use cases
- **Good operability** means having good visibility into the system's health and effective ways of managing it

## What's Next

- There are recurring **patterns and techniques** that appear in different kinds of applications.
- The next few chapters look at examples of data systems and analyze how they work toward these goals.
- **Part III** covers patterns for systems made of several components working together (e.g., the composite data system combining cache, database, search index, and message queue).

## Key Takeaways

1. Applications have **functional** and **nonfunctional** requirements; this chapter focused on three: reliability, scalability, maintainability.
2. **Reliability** — work correctly despite hardware, software, and human faults.
3. **Scalability** — keep performance good under load; describe load quantitatively and measure with percentiles.
4. **Maintainability** — better life for engineering/ops; abstractions reduce complexity; operability gives visibility and control.
5. There is **no easy fix** — but recurring patterns and techniques guide the rest of the book.

## Discussion Questions

1. What are the most important concepts from this chapter?
2. How do these concepts apply to systems you work with?
3. What questions do you have about the material?
4. How do functional and nonfunctional requirements differ? Give examples of each.
5. Why is there no "one-size-fits-all" for reliability, scalability, and maintainability?

## Notes

```markdown
Write your notes here...
```

## Next

- [Chapter 2: Data Models and Query Languages](../../Chapter%2002%20-%20Data%20Models%20and%20Query%20Languages/index.md)
