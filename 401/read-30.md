# Reading 30: Hash Tables

## WHY — Why Use Hash Tables?

Hash tables allow us to store and retrieve data efficiently using a key instead of searching through every item.

For example, looking up a student's grade by their name rather than checking an entire list.

## WHAT — How Do Hash Tables Work?

A hash table stores data as **key-value pairs**.

- **Key:** Identifies the data, such as `"Alex"`.
- **Value:** The information stored, such as `88`.
- **Hash Function:** Converts a key into a number used to determine where data is stored.
- **Bucket:** A location in the table that holds data.
- **Collision:** When two different keys map to the same bucket.

## HOW — Simple Example

Imagine storing student grades:

```javascript
const grades = {
  Alex: 88,
  Moni: 81,
  Jordan: 92
};

console.log(grades["Moni"]); // 81
```

A hash table uses a hash function to determine where each key-value pair belongs.

### What Happens During a Collision?

If `"Alex"` and `"Moni"` map to the same bucket, the hash table needs a way to store both entries.

One solution is **separate chaining**, where a bucket holds multiple key-value pairs.  A collision occurs when different keys are assigned to the same bucket. For example, if `"Alex"` and `"Moni"` both hash to bucket 2, the hash table must distinguish between them. Separate chaining allows multiple key-value pairs to share a bucket, while still keeping their keys and values separate. This helps explain why hash tables usually provide O(1) lookups, but can slow down when many collisions occur.

## Big O Efficiency

| Operation | Average Time |
|---|---|
| Insert | O(1) |
| Search | O(1) |
| Delete | O(1) |

Performance can degrade to O(n) in the worst case when many collisions occur.

## Key Takeaway

Hash tables make retrieving information fast by using keys and hash functions. Understanding buckets and collisions explains why they are efficient and how they handle multiple values mapping to the same location.