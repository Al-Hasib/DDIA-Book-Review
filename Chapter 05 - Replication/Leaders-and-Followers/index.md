# Leaders and Followers

## Key Points

### Leader-Based Replication
- One leader (primary) accepts writes
- Followers (replicas) read from leader
- Leader sends changes to followers
- Most common replication approach

### Synchronous vs Asynchronous Replication

#### Synchronous
- Leader waits for follower confirmation
- Guarantees data is up-to-date
- Higher latency
- Risk of blocking if follower fails

#### Asynchronous
- Leader doesn't wait for followers
- Better performance
- Risk of data loss
- Most systems use semi-synchronous

### Setting Up New Followers
1. Take consistent snapshot of leader
2. Copy snapshot to new follower
3. Replay changes from snapshot to current
4. Start accepting reads

### Handling Node Outages
- Follower failover: Other followers continue
- Leader failover: Elect new leader
- Automatic vs manual failover

### Implementation of Replication Logs
- **Statement-based**: Log SQL statements
- **Write-ahead log (WAL)**: Log physical changes
- **Logical logging**: Log row-level changes
- **Trigger-based**: Application-level replication

## Discussion Questions
1. When would you choose synchronous over asynchronous replication?
2. What are the risks of automatic failover?
3. How does logical logging differ from physical logging?

## Notes

```markdown
Write your notes here...
```
