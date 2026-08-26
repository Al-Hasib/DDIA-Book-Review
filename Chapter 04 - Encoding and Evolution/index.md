# Chapter 4: Encoding and Evolution

> "Change is the only constant."

## Overview

This chapter explores how data is serialized and how systems evolve over time. Encoding formats and dataflow patterns are critical for system evolution.

## What You'll Learn

1. **Formats for Encoding Data** - JSON, XML, Thrift, Protocol Buffers, Avro
2. **Modes of Dataflow** - Through databases, services, and message queues

## Video Outline

### Part 1: Introduction (5 min)
- Why encoding matters
- The challenge of evolution

### Part 2: Encoding Formats (25 min)
- Language-specific formats
- JSON, XML, and binary variants
- Thrift and Protocol Buffers
- Avro

### Part 3: Modes of Dataflow (25 min)
- Dataflow through databases
- Dataflow through services (REST and RPC)
- Message-passing dataflow

### Part 4: Summary (5 min)
- Key takeaways
- What's next

## Sections

- [Formats for Encoding Data](Formats-for-Encoding-Data/index.md)
- [Modes of Dataflow](Modes-of-Dataflow/index.md)
- [Summary](Summary/index.md)

## Key Concepts

- **Encoding**: Converting data to bytes for storage or transmission
- **Schema evolution**: Changing data format without breaking systems
- **Forward/backward compatibility**: Handling different versions

## Practice Questions

1. What are the tradeoffs between JSON and Protocol Buffers?
2. How does Avro handle schema evolution?
3. What is the difference between REST and RPC?
4. How do message queues enable decoupled systems?

## Additional Resources

- [Protocol Buffers Documentation](https://developers.google.com/protocol-buffers)
- [Apache Avro Documentation](https://avro.apache.org/)
- [gRPC Documentation](https://grpc.io/)
