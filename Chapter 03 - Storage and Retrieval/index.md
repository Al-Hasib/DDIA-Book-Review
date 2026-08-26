# Chapter 3: Storage and Retrieval

> "The devil is in the details."

## Overview

This chapter explores how databases store and retrieve data. Understanding the storage engine is crucial for optimizing performance and choosing the right database for your use case.

## What You'll Learn

1. **Data Structures That Power Your Database** - Hash indexes, SSTables, B-Trees
2. **Transaction Processing or Analytics** - OLTP vs OLAP
3. **Column-Oriented Storage** - Why columns matter for analytics

## Video Outline

### Part 1: Introduction (5 min)
- Why storage matters
- Two main use cases: OLTP and OLAP

### Part 2: Data Structures (30 min)
- Hash indexes
- SSTables and LSM-Trees
- B-Trees
- Comparing B-Trees and LSM-Trees

### Part 3: Transaction Processing vs Analytics (15 min)
- OLTP (Online Transaction Processing)
- OLAP (Online Analytical Processing)
- Data warehousing
- Stars and snowflakes schemas

### Part 4: Column-Oriented Storage (20 min)
- Why column-oriented storage
- Column compression
- Sort order in column storage
- Writing to column-oriented storage

### Part 5: Summary (5 min)
- Key takeaways
- What's next

## Sections

- [Data Structures That Power Your Database](Data-Structures-That-Power-Your-Database/index.md)
- [Transaction Processing or Analytics](Transaction-Processing-or-Analytics/index.md)
- [Summary](Summary/index.md)

## Key Concepts

- **OLTP**: Transaction-oriented, many small reads/writes
- **OLAP**: Analytics-oriented, few large reads
- **B-Trees**: Most common index structure
- **LSM-Trees**: Write-optimized alternative

## Practice Questions

1. What are the differences between hash indexes and B-Trees?
2. When would you use an LSM-Tree over a B-Tree?
3. What is the difference between OLTP and OLAP?
4. Why is column-oriented storage better for analytics?
5. What are data cubes and materialized views?

## Additional Resources

- [B-Tree Visualization](https://www.cs.usfca.edu/~galles/visualization/BST.html)
- [LSM-Tree Paper](http://www.vldb.org/pvldb/vol8/p201-athanassoulis.pdf)
- [Column-Oriented Databases](https://www.vertica.com/)
