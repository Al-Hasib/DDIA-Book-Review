# Problems with Replication Lag

## Video Timestamp
[00:20:00] - Problems with Replication Lag

## Key Points

### Reading Your Own Writes
- Problem: User writes data, then reads from stale follower
- Solutions:
  - Read from leader after write
  - Track write timestamps
  - Read-your-writes consistency

### Monotonic Reads
- Problem: Reading from different followers at different times
- Result: Going back in time
- Solution: Stick to one follower per session

### Consistent Prefix Reads
- Problem: Followers see writes in different order
- Solution: Causal ordering of writes

### Solutions for Replication Lag
- **Read-after-write consistency**: Ensure user sees their writes
- **Monotonic reads**: Consistent ordering
- **Consistent prefix**: Causal ordering
- Transaction conflicts and causal consistency

## Discussion Questions
1. How would you implement read-your-writes consistency?
2. What are the tradeoffs of each solution?
3. How does replication lag affect user experience?

## Notes

```markdown
Write your notes here...
```
