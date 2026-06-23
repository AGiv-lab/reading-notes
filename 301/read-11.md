# MongoDB and Mongoose Notes

## SQL vs NoSQL

| SQL | NoSQL |
|------|--------|
| Relational database | Non-relational database |
| Uses tables, rows, and columns | Uses documents, key-value pairs, graphs, etc. |
| Fixed schema | Flexible schema |
| Uses SQL queries | Uses database-specific queries |
| Better for complex relationships | Better for large-scale distributed data |

---

## SQL Databases

### Best For
- Structured data
- Clear relationships between data
- Consistent data formats

### Real-World Example
- Banking systems
  - Customers
  - Accounts
  - Transactions

### Key Features
- Data stored in tables
- Uses rows and columns
- Strong data consistency
- Uses SQL (Structured Query Language)

---

## NoSQL Databases

### Best For
- Unstructured or changing data
- Fast scaling
- Flexible data models

### Real-World Example
- Social media platforms
  - User profiles
  - Posts
  - Comments
  - Activity feeds

### Key Features
- Data stored as documents, key-value pairs, graphs, or columns
- Flexible schema
- Easy to scale across multiple servers

---

## Hierarchical Data Storage

### Best Choice
**NoSQL**

### Why?
- Supports nested documents
- Handles parent-child relationships naturally
- Good for tree-like data structures

Example:
```json
{
  "category": "Animals",
  "children": [
    {
      "category": "Mammals"
    }
  ]
}
```

---

## Scalability

### Best Choice
**NoSQL**

### Why?
- Designed for horizontal scaling
- Can distribute data across multiple servers
- Handles large amounts of traffic and data

---

# Video Notes

## 1. What Does SQL Stand For?

**Structured Query Language**

---

## 2. What Is a Relational Database?

A database that stores data in related tables.

---

## 3. What Structure Does a Relational Database Use?

- Tables
- Rows
- Columns

Example:

| ID | Name |
|----|------|
| 1 | Alice |
| 2 | Bob |

---

## 4. What Is a Schema?

A blueprint that defines:
- Data structure
- Data types
- Relationships between data

Think of it as the database's rules.

---

## 5. What Is a NoSQL Database?

A non-relational database designed for:
- Flexibility
- Scalability
- Large amounts of data

---

## 6. How Does NoSQL Work?

Stores data as:
- Documents
- Key-value pairs
- Graphs
- Wide-column data

Instead of traditional tables.

---

## 7. What Is Inside a MongoDB Database?

### Database
Contains: Collections

### Collections
Contain: documents

### Documents  *stores data in an objects like form*

Example:

```json
{
  "name": "Alice",
  "age": 25
}
```

---

## SQL vs MongoDB Flexibility

### More Flexible?
**MongoDB**

### Why?
- Documents can have different fields
- Schema can change easily
- No need to redesign tables when data changes

---

## 9. Disadvantages of NoSQL

- Weaker support for complex relationships
- May have weaker data consistency
- Complex queries can be harder than SQL

---

# Quick Study Guide

### SQL
- Tables
- Rows & columns
- Fixed schema
- Strong relationships
- Best for structured data

### NoSQL
- Documents
- Flexible schema
- Easier scaling
- Best for changing or unstructured data

### MongoDB
- NoSQL database
- Uses collections and documents
- Highly flexible
- Good for modern web applications

# SQL vs NoSQL Quick Notes

## Common SQL Databases

- MySQL
- PostgreSQL
- Microsoft SQL Server
- Oracle Database
- SQLite
- MariaDB

### SQL Characteristics

- Uses tables
- Stores data in rows and columns
- Fixed schema
- Uses SQL queries
- Strong relationships between data
- Best for structured data

---

## Common NoSQL Databases

- MongoDB
- Cassandra
- Redis
- CouchDB
- Neo4j
- Amazon DynamoDB

### NoSQL Characteristics

- Uses documents, key-value pairs, graphs, or columns
- Flexible schema
- Easier horizontal scaling
- Good for large and changing datasets
- Best for unstructured or rapidly changing data

---

## Quick Interview Cheat Sheet

| SQL | NoSQL |
|------|--------|
| MySQL | MongoDB |
| PostgreSQL | Cassandra |
| SQL Server | Redis |
| Oracle Database | CouchDB |
| SQLite | DynamoDB |
| MariaDB | Neo4j |

---

## Easy Way to Remember

| SQL | MongoDB / NoSQL |
|------|------|
| Database | Database |
| Table | Collection |
| Row | Document |
| Column | Field |

---

## Best Uses

| Use Case | Best Choice |
|-----------|------------|
| Banking System | SQL |
| Inventory System | SQL |
| Social Media App | NoSQL |
| Real-Time Analytics | NoSQL |
| Hierarchical Data | NoSQL |
| Maximum Scalability | NoSQL |