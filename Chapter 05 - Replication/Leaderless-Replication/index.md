# Leaderless Replication

## Key Points

### Writing to the Database When a Node Is Down
- No single leader to coordinate
- Clients send writes to multiple replicas
- Quorum determines success

### Limitations of Quorum Consistency
- **r + w > n**: Quorum condition
- **r**: Number of reads
- **w**: Number of writes
- **n**: Total replicas

### Sloppy Quorums and Hinted Handoff
- When quorum unavailable
- Write to any available nodes
- Forward to correct nodes later

### Detecting Concurrent Writes
- **Vector clocks**: Track causality
- **Last-write wins**: Simple but lossy
- **Conflict resolution**: Application-level

## Discussion Questions
1. What are the advantages of leaderless replication?
2. How do you choose r and w values?
3. How do vector clocks work?

## Notes

```markdown
Write your notes here...
```
