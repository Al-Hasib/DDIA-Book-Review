# Request Routing

## Video Timestamp
[00:50:00] - Request Routing

## Key Points

### Routing Strategies
- **Client-side routing**: Client knows partition layout
- **Routing tier**: Load balancer routes requests
- **Partition-aware clients**: Client tracks partition assignments

### Parallel Query Execution
- Scatter-gather to multiple partitions
- Combine results
- Can be slow if partitions on different nodes

### Service Discovery
- How clients find the right node
- ZooKeeper, etcd for coordination
- Gossip protocol for decentralized discovery

## Discussion Questions
1. When would you choose client-side vs routing tier routing?
2. How do you handle partition movement during routing?
3. What are the tradeoffs of each approach?

## Notes

```markdown
Write your notes here...
```
