# Scalability

## Video Timestamp
[00:25:00] - Scalability Section

## Key Points

### What is Scalability?
- The system's ability to cope with increased load
- Need to define load and performance metrics

### Describing Load

#### Key Metrics
- **Requests per second** (throughput)
- **Response time** (latency)
- **Cache hit rate**

#### Load Parameters
- Different systems have different load parameters
- Twitter: tweets per second, followers per user
- Netflix: streaming bitrate, concurrent viewers
- Amazon: requests per second, items in cart

### Describing Performance

#### Throughput vs Latency
- **Throughput**: Number of operations per second
- **Latency**: Time to complete an operation

#### Percentiles
- **p50 (median)**: 50% of requests complete in this time
- **p95**: 95% of requests complete in this time
- **p99**: 99% of requests complete in this time
- Tail latency matters for large-scale systems

### Approaches for Coping with Load

#### Scaling Approaches
1. **Vertical scaling (scaling up)**: Bigger machine
2. **Horizontal scaling (scaling out)**: More machines

#### Architectural Patterns
- Shared-nothing architecture
- Caching
- Read replicas
- Sharding
- Load balancing

## Discussion Questions
1. How would you describe load for a ride-sharing app like Uber?
2. Why is tail latency important in large-scale systems?
3. What are the tradeoffs between vertical and horizontal scaling?

## Notes

```markdown
Write your notes here...
```
