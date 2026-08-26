# Graph-Like Data Models

## Video Timestamp
[00:45:00] - Graph-Like Data Models

## Key Points

### When Graphs Are Useful
- Highly connected data
- Many-to-many relationships
- Social networks, knowledge graphs, recommendation systems

### Property Graphs
- Each node and edge can have properties
- Nodes can have labels
- Edges have relationships and directions

### The Cypher Query Language
- Query language for property graphs (Neo4j)
- Pattern matching syntax
- Very expressive for graph queries

```cypher
MATCH (person:Person)-[:ACTED_IN]->(movie:Movie)
WHERE person.name = 'Tom Hanks'
RETURN movie.title
```

### Graph Queries in SQL
- Recursive common table expressions (CTEs)
- Can traverse graphs but more verbose
- Performance may not be optimal

### Triple-Stores and SPARQL
- Data as subject-predicate-object triples
- RDF (Resource Description Framework)
- SPARQL is the query language for RDF
- Used in knowledge graphs (Wikidata, DBpedia)

### The Foundation: Datalog
- Logic programming language
- Basis for many query languages
- Declarative and recursive

## Discussion Questions
1. When would you choose a graph database over a relational database?
2. What are the advantages of SPARQL for knowledge graphs?
3. How does Datalog relate to Prolog?

## Notes

```markdown
Write your notes here...
```
