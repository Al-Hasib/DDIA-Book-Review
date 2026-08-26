# Formats for Encoding Data

## Video Timestamp
[00:00:00] - Introduction

## Key Points

### Language-Specific Formats
- Java Serialization, Python pickle
- **Problems**: Tied to specific language, security issues, versioning difficulties

### JSON, XML, and Binary Variants

#### JSON
- Human-readable
- Widely supported
- No schema enforcement
- Verbose

#### XML
- More structured than JSON
- Schema support (XSD)
- Very verbose
- Complex parsing

#### Binary Variants
- MessagePack, BSON, CBOR
- More compact than text formats
- Still schemaless

### Thrift and Protocol Buffers

#### Thrift
- Developed by Facebook
- Interface Definition Language (IDL)
- Binary encoding
- Good for RPC

#### Protocol Buffers
- Developed by Google
- Similar to Thrift
- More widespread adoption
- Better tooling

### Avro
- Developed for Hadoop
- Schema embedded in data
- Excellent schema evolution
- Compact binary format

### The Merits of Schemas
- Schema evolution is essential
- Forward and backward compatibility
- Documentation and validation

## Discussion Questions
1. When would you choose JSON over Protocol Buffers?
2. How does Avro handle schema evolution better than JSON?
3. What are the security implications of language-specific formats?

## Notes

```markdown
Write your notes here...
```
