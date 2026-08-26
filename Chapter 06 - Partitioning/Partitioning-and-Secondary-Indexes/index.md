# Partitioning and Secondary Indexes

## Video Timestamp
[00:20:00] - Secondary Indexes

## Key Points

### Partitioning Secondary Indexes by Document
- Each partition has its own secondary index
- Write: Update only affected partition
- Read: Scatter-gather to all partitions
- Simple but slow reads

### Partitioning Secondary Indexes by Term
- Global secondary index
- Term → list of partitions
- Write: Update all partitions
- Read: Only query relevant partition
- Fast reads but slow writes

## Discussion Questions
1. When would you choose document partitioning over term partitioning?
2. How do you handle distributed secondary indexes?
3. What are the tradeoffs of each approach?

## Notes

```markdown
Write your notes here...
```
