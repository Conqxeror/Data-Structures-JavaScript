# Collision Handling Techniques in Hash Tables

In hash tables, collisions occur when two different keys produce the same hash code, and there is an attempt to store these keys at the same location in the table. Collision handling techniques are used to resolve these situations and efficiently store and retrieve key-value pairs.

## Common Collision Handling Techniques

1. **Separate Chaining**: In this technique, each slot in the hash table stores a linked list (or other data structure) to accommodate multiple key-value pairs with the same hash code.

2. **Open Addressing**: In this technique, when a collision occurs, the algorithm searches for the next available slot within the table. Common open addressing methods include linear probing, quadratic probing, and double hashing.

## JavaScript Implementation (Separate Chaining)

Here's an example of implementing collision handling using separate chaining in JavaScript:

```javascript
class HashTable {
  constructor(tableSize) {
    this.tableSize = tableSize;
    this.data = new Array(tableSize);
  }

  // Hash function (as discussed in the previous example)

  // Insert a key-value pair into the hash table using separate chaining
  set(key, value) {
    const index = simpleHash(key, this.tableSize);
    if (!this.data[index]) {
      this.data[index] = [];
    }
    this.data[index].push({ key, value });
  }

  // Retrieve the value associated with a key using separate chaining
  get(key) {
    const index = simpleHash(key, this.tableSize);
    const bucket = this.data[index];
    if (bucket) {
      for (const pair of bucket) {
        if (pair.key === key) {
          return pair.value;
        }
      }
    }
    return undefined; // Key not found
  }

  // Other methods like delete and has can be implemented here
}

// Usage example
const tableSize = 10;
const hashTable = new HashTable(tableSize);
hashTable.set("name", "John");
hashTable.set("age", 30);

const name = hashTable.get("name"); // "John"
