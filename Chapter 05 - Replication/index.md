# Chapter 5: Replication

> "The only way to go fast is to go well."

## Overview

This chapter explores replication: keeping copies of the same data on multiple machines. Replication helps with performance, reliability, and latency.

## What You'll Learn

1. **Leaders and Followers** - Primary-backup replication
2. **Multi-Leader Replication** - Multiple leaders
3. **Leaderless Replication** - No single leader

## Video Outline

### Part 1: Introduction (5 min)
- Why replicate data
- Three main approaches

### Part 2: Leaders and Followers (20 min)
- Synchronous vs asynchronous replication
- Setting up new followers
- Handling node outages
- Implementation of replication logs

### Part 3: Problems with Replication Lag (15 min)
- Reading your own writes
- Monotonic reads
- Consistent prefix reads

### Part 4: Multi-Leader Replication (15 min)
- Use cases
- Handling write conflicts
- Topologies

### Part 5: Leaderless Replication (20 min)
- Writing when nodes are down
- Quorum consistency
- Sloppy quorums
- Detecting concurrent writes

### Part 6: Summary (5 min)

## Sections

- [Leaders and Followers](Leaders-and-Followers/index.md)
- [Problems with Replication Lag](Problems-with-Replication-Lag/index.md)
- [Multi-Leader Replication](Multi-Leader-Replication/index.md)
- [Leaderless Replication](Leaderless-Replication/index.md)
- [Summary](Summary/index.md)

## Key Concepts

- **Leader-based replication**: One leader, many followers
- **Multi-leader replication**: Multiple leaders accept writes
- **Leaderless replication**: No single leader
- **Consistency**: How up-to-date followers are

## Practice Questions

1. What are the tradeoffs between synchronous and asynchronous replication?
2. How do you handle write conflicts in multi-leader replication?
3. What is a quorum and how does it work?
4. How do you detect concurrent writes in leaderless systems?

## Additional Resources

- [Kafka Replication](https://kafka.apache.org/documentation/#replication)
- [Cassandra Architecture](https://cassandra.apache.org/doc/latest/architecture/)
- [Dynamo Paper](https://www.allthingsdistributed.com/files/amazon-dynamo-sosp2007.pdf)
