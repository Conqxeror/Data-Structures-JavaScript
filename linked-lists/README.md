# Introduction to Linked Lists in JavaScript

A linked list is a linear data structure used for organizing and storing a collection of elements called nodes. Unlike arrays, linked lists do not store elements in contiguous memory locations. Instead, each node contains data and a reference (or link) to the next node in the sequence. This makes linked lists flexible and efficient for dynamic data storage.

## Advantages of Linked Lists

- **Dynamic Size**: Linked lists can grow or shrink as needed since memory allocation is not fixed.
- **Insertion and Deletion**: Adding or removing elements can be done efficiently by updating links.
- **No Wasted Space**: Linked lists use only as much memory as needed for the data.
- **Constant-Time Insertions and Deletions**: If you have a reference to the node, you can insert or delete it in constant time.

## Types of Linked Lists

1. **Singly Linked List**: Each node contains data and a reference to the next node.
2. **Doubly Linked List**: Each node contains data and references to both the next and previous nodes.
3. **Circular Linked List**: Similar to singly or doubly linked lists but with the last node pointing back to the first node.

## JavaScript Implementation (Singly Linked List)

Here's an example of implementing a singly linked list in JavaScript:

```js
class Node {
  constructor(data) {
    this.data = data;
    this.next = null;
  }
}

class LinkedList {
  constructor() {
    this.head = null;
  }

  // Append a new node to the end of the list
  append(data) {
    const newNode = new Node(data);
    if (!this.head) {
      this.head = newNode;
    } else {
      let current = this.head;
      while (current.next) {
        current = current.next;
      }
      current.next = newNode;
    }
  }

  // Prepend a new node to the beginning of the list
  prepend(data) {
    const newNode = new Node(data);
    newNode.next = this.head;
    this.head = newNode;
  }

  // Delete the first node with the given data
  delete(data) {
    if (!this.head) {
      return;
    }

    if (this.head.data === data) {
      this.head = this.head.next;
      return;
    }

    let current = this.head;
    while (current.next) {
      if (current.next.data === data) {
        current.next = current.next.next;
        return;
      }
      current = current.next;
    }
  }

  // Search for a node with the given data and return it (or null if not found)
  search(data) {
    let current = this.head;
    while (current) {
      if (current.data === data) {
        return current;
      }
      current = current.next;
    }
    return null;
  }

  // Other methods like insertAfter, insertBefore, length, and more can be added here
}

// Example usage
const linkedList = new LinkedList();
linkedList.append(1);
linkedList.append(2);
linkedList.prepend(0);
linkedList.delete(1);
const node = linkedList.search(2);
console.log(node); // Output: Node { data: 2, next: null }
```