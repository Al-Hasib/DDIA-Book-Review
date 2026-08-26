# Query Languages for Data

## Video Timestamp
[00:25:00] - Query Languages

## Key Points

### Declarative vs Imperative Queries

#### Imperative (Tell the computer HOW to do things)
```javascript
function getOrangeCars(cars) {
  const result = [];
  for (const car of cars) {
    if (car.color === "orange") {
      result.push(car);
    }
  }
  return result;
}
```

#### Declarative (Tell the computer WHAT you want)
```sql
SELECT * FROM cars WHERE color = 'orange';
```

### Declarative Queries on the Web
- CSS is declarative (style this element this way)
- HTML is declarative (this is a heading)
- SQL is declarative (query this data this way)
- Benefits: easier to optimize, parallelizable

### MapReduce Querying
- Programming model for batch processing
- Map function processes data in parallel
- Reduce function aggregates results
- Used in Hadoop, MongoDB, CouchDB

#### Example
```javascript
// Map phase
map = function(doc) {
  if (doc.year >= 2010 && doc.year <= 2014) {
    emit(doc.year, 1);
  }
}

// Reduce phase
reduce = function(key, values) {
  return sum(values);
}
```

## Discussion Questions
1. What are the advantages of declarative queries over imperative queries?
2. How does MapReduce relate to functional programming?
3. What are the limitations of MapReduce?

## Notes

```markdown
Write your notes here...
```
