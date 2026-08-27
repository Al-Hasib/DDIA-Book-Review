# Rebalancing Partitions

## Key Points

### Strategies for Rebalancing

#### Fixed Number of Partitions
- Create more partitions than nodes
- Assign multiple partitions per node
- Move partitions when nodes added/removed

#### Dynamic Partitioning
- Split partitions when too large
- Merge partitions when too small
- Automatic rebalancing

#### Proportional to Nodes
- Each node gets partitions
- When node added, steal partitions from others

### Operations: Automatic or Manual Rebalancing

#### Automatic
- System decides when to rebalance
- Risk of cascading failures
- May rebalance unnecessarily

#### Manual
- Operator decides when to rebalance
- More predictable
- More work

## Discussion Questions
1. When would you choose automatic over manual rebalancing?
2. How do you prevent cascading failures during rebalancing?
3. What are the tradeoffs of fixed vs dynamic partitioning?

## Notes

```markdown
Write your notes here...
```
