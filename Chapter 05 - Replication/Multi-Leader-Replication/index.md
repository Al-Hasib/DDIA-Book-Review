# Multi-Leader Replication

## Video Timestamp
[00:35:00] - Multi-Leader Replication

## Key Points

### Use Cases for Multi-Leader Replication
- Multi-datacenter operation
- Offline-first applications
- Collaborative editing
- Better write performance

### Handling Write Conflicts
- **Last write wins**: Simple but loses data
- **Merge values**: Combine changes
- **Preserve all versions**: Let application resolve
- **Conflict-free replicated data types (CRDTs)**

### Multi-Leader Replication Topologies
- **Star**: All leaders connect to one
- **Circle**: Leaders in a ring
- **All-to-full**: Every leader connects to every other
- **Custom**: Any topology

## Discussion Questions
1. When would you choose multi-leader over single-leader?
2. How do CRDTs work for conflict resolution?
3. What are the risks of multi-leader replication?

## Notes

```markdown
Write your notes here...
```
