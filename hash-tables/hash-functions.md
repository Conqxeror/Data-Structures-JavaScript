# Hash Functions in JavaScript

A hash function is a function that takes an input (or "key") and returns a fixed-size string or number, which is typically a hash code. Hash functions play a crucial role in hash tables, as they determine the location where key-value pairs are stored and retrieved efficiently.

## Characteristics of Good Hash Functions

A good hash function should have the following characteristics:

1. **Deterministic**: For the same input, it should always produce the same hash code.
2. **Efficient**: It should compute the hash code quickly.
3. **Uniform Distribution**: It should distribute hash codes evenly across the available slots in the hash table.
4. **Collision Resistance**: It should minimize collisions (different keys mapping to the same hash code).
5. **Avalanche Effect**: A small change in the input should result in a significantly different hash code.

## JavaScript Implementation (Hash Function)

Here's an example of implementing a simple hash function in JavaScript:

```javascript
function simpleHash(key, tableSize) {
  let hash = 0;
  for (let i = 0; i < key.length; i++) {
    hash += key.charCodeAt(i);
  }
  return hash % tableSize;
}

// Usage example
const key = "example";
const tableSize = 10;
const hash = simpleHash(key, tableSize); // Computed hash code
```