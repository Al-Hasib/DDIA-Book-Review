# Summary

## Key Takeaways

### Partitioning Strategies
- **Key range**: Good for range queries, risk of hot spots
- **Hash of key**: Good for random access, even distribution
- **Skewed workloads**: Need special handling

### Secondary Indexes
- **Document partitioning**: Simple but slow reads
- **Term partitioning**: Fast reads but slow writes

### Rebalancing
- Fixed, dynamic, or proportional strategies
- Automatic vs manual tradeoffs
- Prevent cascading failures

### Request Routing
- Client-side, routing tier, or partition-aware
- Service discovery is essential
- Scatter-gather for parallel queries

### What's Next
- Chapter 7: Transactions
- How to ensure consistency in concurrent operations

## Discussion Questions
1. What are the most important concepts from this chapter?
2. How do these concepts apply to systems you work with?
3. What questions do you have about the material?

## Notes

```markdown
Write your notes here...
```
