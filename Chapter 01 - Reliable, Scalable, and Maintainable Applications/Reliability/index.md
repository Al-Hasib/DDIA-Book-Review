# Reliability

## Overview

Everybody has an intuitive idea of what it means for something to be reliable or unreliable. Roughly, **reliability means "continuing to work correctly, even when things go wrong."**

## What You'll Learn

1. What "working correctly" actually means
2. Faults vs. failures
3. Hardware, software, and human faults
4. Why reliability matters—even for "noncritical" apps

## What "Working Correctly" Means

For software, typical expectations include:

- The application performs the **function** the user expected
- It **tolerates the user making mistakes** or using the software in unexpected ways
- Its **performance is good enough** for the required use case, under expected load and data volume
- The system **prevents unauthorized access and abuse**

If all of those together mean "working correctly," then reliability is "continuing to work correctly, even when things go wrong."

## Faults vs. Failures

The things that go wrong are called **faults**. Systems that anticipate faults and cope with them are called **fault-tolerant** or **resilient**.

The term "fault-tolerant" is slightly misleading—it suggests you could tolerate *every possible* fault, which isn't feasible. (If the planet were swallowed by a black hole, tolerance would require web hosting in space.) So it only makes sense to talk about tolerating **certain types** of faults.

Key distinction:

- **Fault** — one component of the system deviating from its spec
- **Failure** — the system as a whole stops providing the required service to the user

> It is impossible to reduce the probability of a fault to zero, so design **fault-tolerance mechanisms that prevent faults from causing failures.**

### Deliberately Inducing Faults

Counterintuitively, in fault-tolerant systems it can make sense to **increase the rate of faults by triggering them deliberately**—e.g., randomly killing processes without warning. Many critical bugs are due to poor error handling. Deliberately inducing faults ensures the fault-tolerance machinery is continually tested.

- Example: **Netflix's Chaos Monkey**

### When Prevention Is Better Than Cure

Although we generally prefer tolerating faults, some faults can't be cured. This is especially true with **security**: if an attacker has compromised a system, that event cannot be undone. This book focuses mostly on faults that *can* be cured.

## Hardware Faults

When we think of causes of failure, hardware faults come to mind first: hard disks crash, RAM becomes faulty, power outages, someone unplugs the wrong cable.

With a storage cluster of **10,000 disks** (MTTF ~10–50 years), expect **on average one disk to die per day**.

### First Response: Hardware Redundancy

- **RAID** configurations for disks
- **Dual power supplies** and hot-swappable CPUs
- Batteries and **diesel generators** for backup power

When one component dies, the redundant component takes over. This doesn't fully prevent failures, but it's well understood and can keep a machine running uninterrupted for years.

### The Shift Toward Software Fault Tolerance

Multi-machine redundancy used to be required only for a few high-availability apps. But today:

1. **Data volumes and computing demands** have grown → more machines → proportionally more hardware faults
2. **Cloud platforms like AWS** tolerate VMs becoming unavailable without warning, prioritizing flexibility/elasticity over single-machine reliability

So there's a move toward systems that **tolerate the loss of entire machines** using software fault-tolerance, in preference to (or addition to) hardware redundancy. This also has operational advantages—e.g., a **rolling upgrade** lets you patch one node at a time without downtime of the whole system.

## Software Errors

Hardware faults are usually **random and independent**. Software faults are different: they're **systematic errors** that are correlated across nodes, so they tend to cause far more system failures.

Examples include:

- A **bug** that crashes every instance on a particular bad input (e.g., the 2012 leap second bug causing many apps to hang)
- A **runaway process** using up a shared resource (CPU, memory, disk, bandwidth)
- A **dependent service** that slows down or returns corrupted responses
- **Cascading failures** — a small fault in one component triggers faults in others

These bugs often lie dormant until triggered by unusual circumstances, revealing that the software assumed something about its environment that eventually stopped being true.

### No Quick Solution

There's no quick fix for systematic software faults, but many small things help:

- Carefully thinking about **assumptions and interactions**
- **Thorough testing**
- **Process isolation**
- Allowing processes to **crash and restart**
- **Measuring, monitoring, and analyzing** behavior in production
- Systems that **self-check** (e.g., a message queue verifying incoming messages equal outgoing ones) and raise alerts on discrepancy

## Human Errors

Humans design and build systems, and operators are human too. One study found **configuration errors by operators were the leading cause of outages**, while hardware faults played a role in only **10–25%** of outages.

### How to Make Systems Reliable Despite Unreliable Humans

The best systems combine several approaches:

1. **Minimize opportunities for error** — well-designed abstractions, APIs, and admin interfaces make it easy to do the right thing (but not too restrictive, or people work around them)
2. **Decouple mistakes from failures** — provide sandbox environments where people can experiment safely with real data
3. **Test thoroughly at all levels** — unit tests to integration tests and manual tests, especially for corner cases
4. **Allow quick recovery from human error** — fast rollbacks, gradual rollouts, tools to recompute data
5. **Detailed monitoring (telemetry)** — performance metrics and error rates that give early warning and help diagnose issues
6. **Good management practices and training** (beyond the scope of this book)

## How Important Is Reliability?

Reliability isn't just for nuclear power stations and air traffic control. More mundane applications are expected to work reliably:

- **Bugs** in business applications cause lost productivity (and legal risk if figures are wrong)
- **Outages** of ecommerce sites cost lost revenue and reputation damage
- Even "noncritical" apps have responsibility to users (e.g., a parent storing photos of their children in your app)

There *are* situations to deliberately sacrifice reliability to reduce development or operational cost (e.g., a prototype for an unproven market)—but we should be **very conscious of when we're cutting corners**.

## Key Takeaways

1. Reliability = **continuing to work correctly even when things go wrong**.
2. **Fault ≠ failure** — design mechanisms that prevent faults from causing failures.
3. Hardware faults → **hardware redundancy**, shifting toward **software fault tolerance** for whole machines.
4. Software faults are **systematic and correlated** → much harder to predict; mitigate with testing, isolation, monitoring.
5. **Human errors** cause the most outages — design to minimize, decouple, and recover.
6. Reliability matters even for mundane apps; sacrifices should be conscious.

## Discussion Questions

1. What's the difference between a fault and a failure? Give an example of each.
2. What are some examples of hardware faults you've experienced?
3. How can software errors lead to cascading failures?
4. What are some strategies for preventing human errors?
5. Why is it useful to deliberately induce faults (e.g., Chaos Monkey)?
6. When might it be acceptable to sacrifice reliability?

## Notes

```markdown
Write your notes here...
```

## Next

- [Scalability](Scalability/index.md) — Handling increased load
- [Maintainability](Maintainability/index.md) — Keeping systems healthy over time
