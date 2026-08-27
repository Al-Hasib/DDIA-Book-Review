# Partitioning of Key-Value Data

## Key Points

### Partitioning by Key Range
- Assign ranges to partitions
- Good for range queries
- Risk of hot spots
- Manual rebalancing needed

### Partitioning by Hash of Key
- Hash function distributes evenly
- Good for random access
- Bad for range queries
- Automatic rebalancing possible

### Skewed Workloads and Relieving Hot Spots
- Some keys more popular than others
- Hot spots cause uneven load
- Solutions:
  - Replicate hot keys
  - Application-level sharding
  - Random suffixes

## Discussion Questions
1. When would you choose key range over hash partitioning?
2. How do you detect and handle hot spots?
3. What are the tradeoffs of each approach?

## Notes

```markdown
Write your notes here...
```
