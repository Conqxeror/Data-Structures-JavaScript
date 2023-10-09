# Doubly Linked List in JavaScript

A doubly linked list is an extension of the singly linked list where each node has two references: one to the next node and another to the previous node. This bidirectional linking allows for more versatile operations compared to singly linked lists.

## Advantages of Doubly Linked Lists

- Bidirectional traversal: You can traverse the list both forwards and backward.
- Efficient insertion and deletion: Insertion and deletion of elements at any position are efficient.

## Operations on Doubly Linked Lists

1. **Insertion**: You can insert a new node at the beginning, end, or anywhere in between the list.
2. **Deletion**: You can delete a node from the list based on its value or position.
3. **Traversal**: You can traverse the list in both forward and backward directions.
4. **Searching**: You can search for a specific value within the list.

## JavaScript Implementation

Here's a simple example of implementing a doubly linked list in JavaScript:

```javascript
class Node {
  constructor(value) {
    this.value = value;
    this.next = null;
    this.prev = null;
  }
}

class DoublyLinkedList {
  constructor() {
    this.head = null;
    this.tail = null;
    this.size = 0;
  }

  // Insert a new node at the end of the list
  append(value) {
    const newNode = new Node(value);
    if (!this.head) {
      this.head = newNode;
      this.tail = newNode;
    } else {
      newNode.prev = this.tail;
      this.tail.next = newNode;
      this.tail = newNode;
    }
    this.size++;
  }

  // Other methods like delete, search, and traverse can be implemented here
}

// Usage example
const myList = new DoublyLinkedList();
myList.append(1);
myList.append(2);
myList.append(3);
```