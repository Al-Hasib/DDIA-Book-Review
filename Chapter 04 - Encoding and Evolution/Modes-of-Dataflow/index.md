# Modes of Dataflow

## Video Timestamp
[00:25:00] - Modes of Dataflow

## Key Points

### Dataflow Through Databases
- Write data to database, read later
- Encoding/decoding happens at application level
- Database is passive storage
- Schema evolution challenges

### Dataflow Through Services: REST and RPC

#### REST (Representational State Transfer)
- HTTP methods (GET, POST, PUT, DELETE)
- Resource-oriented
- Stateless
- Human-readable URLs

#### RPC (Remote Procedure Call)
- Call functions on remote servers
- Treats network as function call
- Examples: gRPC, Thrift, SOAP
- More efficient than REST for some use cases

### Message-Passing Dataflow
- Asynchronous communication
- Message queues (RabbitMQ, Kafka)
- Decouples producers and consumers
- Better fault tolerance

#### Benefits
- Load leveling
- Retry logic
- Fan-out to multiple consumers
- Decoupled systems

## Discussion Questions
1. When would you choose RPC over REST?
2. What are the tradeoffs of message queues?
3. How do message queues help with fault tolerance?

## Notes

```markdown
Write your notes here...
```
