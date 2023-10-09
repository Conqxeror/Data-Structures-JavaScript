# Queue in JavaScript

A queue is a linear data structure that follows the First-In-First-Out (FIFO) principle. In a queue, the first item added is the first one to be removed. Queues are used to manage collections of elements where you need to maintain order and perform operations like enqueue (adding) and dequeue (removing) elements.

## Operations on Queues

1. **Enqueue**: Add an element to the back of the queue.
2. **Dequeue**: Remove and return the front element from the queue.
3. **Peek**: View the front element without removing it.

## Common Use Cases

Queues are used in various scenarios, including but not limited to:

- Task scheduling: Managing tasks or jobs in a specific order.
- Print job management in printers (first-come-first-served).
- Breadth-first search (BFS) in graph algorithms.
- Handling requests in web servers (request queue).

## JavaScript Implementation

In JavaScript, you can implement a queue using arrays or linked lists. Here's an example of implementing a queue using an array:

```js
class Queue {
  constructor() {
    this.items = [];
  }

  enqueue(item) {
    this.items.push(item);
  }

  dequeue() {
    if (this.isEmpty()) {
      return null; // Queue underflow
    }
    return this.items.shift();
  }

  peek() {
    return this.items[0];
  }

  isEmpty() {
    return this.items.length === 0;
  }
}

// Usage example
const queue = new Queue();
queue.enqueue("A");
queue.enqueue("B");
const frontOfQueue = queue.peek(); // "A"
queue.dequeue(); // Removes and returns "A"
```