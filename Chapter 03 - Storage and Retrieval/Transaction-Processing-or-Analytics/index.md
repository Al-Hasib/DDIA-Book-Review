# Transaction Processing or Analytics

## Key Points

### OLTP (Online Transaction Processing)
- Many small, fast transactions
- Read and write individual records
- Latency-sensitive
- Examples: e-commerce, banking, social media

### OLAP (Online Analytical Processing)
- Few complex queries
- Read many records
- Throughput-sensitive
- Examples: business intelligence, reporting

### Data Warehousing
- Separate database for analytics
- ETL (Extract, Transform, Load) process
- Copies data from OLTP systems
- Optimized for read-heavy workloads

### Stars and Snowflakes: Schemas for Analytics

#### Star Schema
- Central fact table
- Dimension tables connect to facts
- Simple, fast queries

#### Snowflake Schema
- Dimension tables normalized
- More complex, but less redundancy
- Can be slower due to joins

### Column-Oriented Storage
- Store data by columns, not rows
- Better for analytics (reading many rows of few columns)
- Better compression
- Examples: Cassandra, HBase, ClickHouse

## Discussion Questions
1. Why separate OLTP and OLAP systems?
2. What are the tradeoffs of ETL?
3. When would you use a snowflake schema over a star schema?

## Notes

```markdown
Write your notes here...
```
