# Hash Tables in JavaScript

A hash table, also known as a hash map, is a data structure that stores key-value pairs and provides efficient retrieval of values based on their keys. Hash tables are widely used for fast data access, indexing, and dictionary-like operations.

## Operations on Hash Tables

Common operations on hash tables include:

- **Insertion**: Adding a key-value pair to the hash table.
- **Deletion**: Removing a key-value pair from the hash table.
- **Retrieval**: Getting the value associated with a specific key.
- **Search**: Checking if a key exists in the hash table.
- **Collision Handling**: Resolving collisions when multiple keys map to the same hash.

## JavaScript Implementation

In JavaScript, you can implement a simple hash table using objects or JavaScript's built-in `Map` data structure. Here's an example of implementing a basic hash table using objects:

```js
class HashTable {
  constructor() {
    this.data = {};
  }

  // Insert a key-value pair into the hash table
  set(key, value) {
    this.data[key] = value;
  }

  // Retrieve the value associated with a key
  get(key) {
    return this.data[key];
  }

  // Remove a key-value pair from the hash table
  delete(key) {
    if (this.data.hasOwnProperty(key)) {
      delete this.data[key];
    }
  }

  // Check if a key exists in the hash table
  has(key) {
    return this.data.hasOwnProperty(key);
  }
}

// Usage example
const hashTable = new HashTable();
hashTable.set("name", "John");
hashTable.set("age", 30);

const name = hashTable.get("name"); // "John"
hashTable.delete("age");
const hasAge = hashTable.has("age"); // false
```