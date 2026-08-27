# Maintainability

> "Good operations can often work around the limitations of bad (or incomplete) software, but good software cannot run reliably with bad operations."

## Overview

It's well known that the **majority of the cost of software is not in initial development, but in ongoing maintenance**—fixing bugs, keeping systems operational, investigating failures, adapting to new platforms, modifying for new use cases, repaying technical debt, adding features.

Many people dislike maintaining "legacy systems"—fixing others' mistakes, outdated platforms, or systems forced to do things they weren't designed for. Every legacy system is unpleasant in its own way. But **we can design software to minimize maintenance pain and avoid creating legacy software ourselves.**

## What You'll Learn

1. Why the majority of software cost is in maintenance
2. The three design principles: **Operability, Simplicity, Evolvability**
3. How to make life easy for operations teams
4. How to manage (reduce) complexity
5. How to make change easy over time

## Three Design Principles

To minimize maintenance pain, this book gives particular attention to three design principles:

1. **Operability** — Make it easy for operations teams to keep the system running smoothly.
2. **Simplicity** — Make it easy for new engineers to understand the system, by removing as much complexity as possible (note: *not* the same as simplicity of the user interface).
3. **Evolvability** — Make it easy for engineers to make changes in the future, adapting for unanticipated use cases as requirements change. Also called **extensibility, modifiability, or plasticity**.

As with reliability and scalability, there are **no easy solutions**—we just strive to think about systems with these three goals in mind.

## Operability: Making Life Easy for Operations

Operations teams are vital to keeping software running smoothly. While some operations can be automated, it's up to humans to set up that automation and ensure it works.

### What a Good Operations Team Does

- **Monitoring** the system's health and quickly restoring service if it goes into a bad state
- **Tracking down the cause** of problems (failures, degraded performance)
- Keeping software and platforms **up to date**, including security patches
- Keeping tabs on **how systems affect each other** so problematic changes are avoided before damage
- **Anticipating future problems** (e.g., capacity planning)
- Establishing good **practices and tools** for deployment and configuration management
- Performing **complex maintenance tasks** (e.g., moving an app to a new platform)
- **Maintaining security** as configuration changes are made
- Defining processes that make operations **predictable** and keep production stable
- **Preserving organizational knowledge** as individual people come and go

### What Data Systems Can Do to Make Operations Easy

Good operability means making **routine tasks easy**, letting the operations team focus on high-value activities. Systems can help by:

- Providing **visibility** into runtime behavior and internals, with good monitoring
- Providing good support for **automation and integration** with standard tools
- **Avoiding dependency on individual machines** (machines can be taken down while the system continues running)
- Providing good **documentation** and an easy-to-understand operational model ("If I do X, Y will happen")
- Providing **good default behavior**, while letting administrators override defaults when needed
- **Self-healing** where appropriate, but allowing **manual control** over system state when needed
- Exhibiting **predictable behavior**, minimizing surprises

## Simplicity: Managing Complexity

Small projects can have simple, expressive code, but as projects grow they often become **complex and difficult to understand**. This complexity slows down everyone who works on the system, increasing maintenance cost. A project mired in complexity is sometimes described as a **big ball of mud**.

### Symptoms of Complexity

- Explosion of the **state space**
- **Tight coupling** of modules
- **Tangled dependencies**
- **Inconsistent naming and terminology**
- **Hacks** aimed at solving performance problems
- **Special-casing** to work around issues elsewhere

When complexity makes maintenance hard, **budgets and schedules are overrun**, and there's a greater risk of introducing bugs (hidden assumptions, unintended consequences, unexpected interactions are easily overlooked). Reducing complexity greatly improves maintainability, so **simplicity should be a key goal**.

### Accidental vs. Inherent Complexity

Making a system simpler doesn't mean reducing functionality—it can mean removing **accidental complexity**. Complexity is *accidental* if it's **not inherent in the problem** the software solves (as seen by users) but arises only from the implementation.

### Abstraction Is the Best Tool

The best tool for removing accidental complexity is **abstraction**—hiding lots of implementation detail behind a clean, simple façade. A good abstraction:

- Can be used for a **wide range of applications**
- Is **more efficient** than reimplementing similar things multiple times
- Leads to **higher-quality software**, as improvements benefit all applications using it

Examples:
- **High-level programming languages** abstract away machine code, CPU registers, and syscalls
- **SQL** abstracts away complex on-disk/in-memory data structures, concurrent requests, and post-crash inconsistencies

**However, finding good abstractions is very hard.** In distributed systems, while there are many good algorithms, it's much less clear how to package them into abstractions that keep complexity manageable. This book keeps an eye out for good abstractions that extract parts of a large system into well-defined, reusable components.

## Evolvability: Making Change Easy

It's extremely unlikely your requirements will stay unchanged forever. Requirements are in **constant flux**: new facts, unanticipated use cases, shifting business priorities, users requesting features, new platforms, legal/regulatory changes, growth forcing architectural changes.

### Agile and Evolvability

**Agile working patterns** provide a framework for adapting to change, and the Agile community developed technical tools and patterns helpful in changing environments—**test-driven development (TDD)** and **refactoring**.

But most Agile discussions focus on a fairly **small, local scale** (a couple of files in the same application). This book searches for ways to increase **agility at the level of a larger data system**—perhaps several different applications or services with different characteristics.

Example question: How would you "refactor" Twitter's home timeline architecture from approach 1 (on-read join) to approach 2 (fan-out cache)?

### Why Use the Word "Evolvability"?

The ease of modifying a data system is closely linked to its **simplicity and abstractions**—simple, easy-to-understand systems are usually easier to modify than complex ones. Since agility at the data-system level is such an important idea, the book uses a distinct word for it: **evolvability**.

## Key Takeaways

1. **Maintenance is the majority of software cost** — design to avoid creating legacy software.
2. Three design principles: **Operability, Simplicity, Evolvability**.
3. **Operability** — make routine ops tasks easy; ops teams keep systems running smoothly.
4. **Simplicity** — remove *accidental* complexity; use good abstractions (more important than docs).
5. **Evolvability** — make change easy over time; closely linked to simplicity and abstractions.

## Discussion Questions

1. How can poor maintainability lead to technical debt?
2. What are some strategies for reducing complexity?
3. How does evolvability relate to agility?
4. What's the difference between accidental and inherent complexity? Give an example.
5. How might you "refactor" a system like Twitter's home timeline from one approach to another?
6. What role do operations teams play, and how can software make their job easier?

## Notes

```markdown
Write your notes here...
```

## Next

- [Summary](Summary/index.md) — Key takeaways from Chapter 1
