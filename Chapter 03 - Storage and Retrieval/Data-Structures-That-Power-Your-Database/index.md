# Data Structures That Power Your Database

## Video Timestamp
[00:00:00] - Introduction

## Key Points

### Hash Indexes
- Key-value pairs
- O(1) lookup
- Good for exact matches
- Not good for range queries
- Implemented with hash tables on disk

### SSTables and LSM-Trees
- **SSTable** (Sorted String Table): Sorted, immutable files
- **LSM-Tree** (Log-Structured Merge-Tree):
  - Write to in-memory buffer (memtable)
  - Periodically flush to disk as SSTable
  - Merge SSTables during compaction
  - Excellent write performance
  - Good read performance with bloom filters

### B-Trees
- Most common index structure
- Balanced tree with branching factor
- In-place updates
- Good read and write performance
- Used in PostgreSQL, MySQL, MongoDB

### Comparing B-Trees and LSM-Trees

| Aspect | B-Trees | LSM-Trees |
|--------|---------|-----------|
| Write performance | Moderate | Excellent |
| Read performance | Excellent | Good |
| Space efficiency | Good | Excellent |
| Write amplification | Lower | Higher |
| Read amplification | Lower | Higher |

### Other Indexing Structures
- Hash indexes for exact matches
- Bitmap indexes for low-cardinality columns
- Full-text indexes for text search

## Discussion Questions
1. Why are LSM-Trees more write-efficient than B-Trees?
2. What is write amplification and why does it matter?
3. How do bloom filters improve LSM-Tree performance?

## Notes

```markdown
Write your notes here...
```
