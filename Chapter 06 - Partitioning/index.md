# Chapter 6: Partitioning

> "Divide and conquer."

## Overview

This chapter explores partitioning: splitting a large dataset into smaller partitions. Partitioning is essential for scalability and performance.

## What You'll Learn

1. **Partitioning and Replication** - How they work together
2. **Partitioning of Key-Value Data** - Different partitioning strategies
3. **Partitioning and Secondary Indexes** - Handling secondary indexes
4. **Rebalancing Partitions** - Moving partitions between nodes
5. **Request Routing** - Finding the right partition

## Video Outline

### Part 1: Introduction (5 min)
- Why partition
- Partitioning vs replication

### Part 2: Partitioning Strategies (15 min)
- Key range partitioning
- Hash of key partitioning
- Skewed workloads and hot spots

### Part 3: Secondary Indexes (15 min)
- Partitioning by document
- Partitioning by term

### Part 4: Rebalancing (15 min)
- Strategies for rebalancing
- Automatic vs manual rebalancing

### Part 5: Request Routing (10 min)
- Routing strategies
- Parallel query execution

### Part 6: Summary (5 min)

## Sections

- [Partitioning and Replication](Partitioning-and-Replication/index.md)
- [Partitioning of Key-Value Data](Partitioning-of-Key-Value-Data/index.md)
- [Partitioning and Secondary Indexes](Partitioning-and-Secondary-Indexes/index.md)
- [Rebalancing Partitions](Rebalancing-Partitions/index.md)
- [Request Routing](Request-Routing/index.md)
- [Summary](Summary/index.md)

## Key Concepts

- **Partitioning**: Splitting data across nodes
- **Key range**: Partition by key ranges
- **Hash partitioning**: Partition by hash of key
- **Rebalancing**: Moving partitions between nodes

## Practice Questions

1. What are the tradeoffs between key range and hash partitioning?
2. How do you handle skewed workloads?
3. What are the challenges of secondary indexes with partitioning?
4. How does rebalancing work in practice?

## Additional Resources

- [Cassandra Partitioning](https://cassandra.apache.org/doc/latest/architecture/)
- [Couchbase Partitioning](https://docs.couchbase.com/server/6.0/architecture/sharded-index.html)
- [Voldemort Partitioning](http://www.project-voldemort.com/voldemort/)
