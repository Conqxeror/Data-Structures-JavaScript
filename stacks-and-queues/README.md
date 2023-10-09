# Stacks and Queues in JavaScript

Stacks and queues are fundamental data structures that represent collections of elements with specific rules for adding and removing items. They are often used in various algorithms and scenarios to manage data efficiently.

## Stacks

A stack is a linear data structure that follows the Last-In-First-Out (LIFO) principle. In a stack, the last item added is the first one to be removed. Stacks are used in scenarios where you need to keep track of a list of items and perform operations like pushing (adding) and popping (removing) elements.

### Operations on Stacks

1. **Push**: Add an element to the top of the stack.
2. **Pop**: Remove and return the top element from the stack.
3. **Peek**: View the top element without removing it.

## Queues

A queue is another linear data structure, but it follows the First-In-First-Out (FIFO) principle. In a queue, the first item added is the first one to be removed. Queues are used in scenarios where you need to maintain order and perform operations like enqueue (adding) and dequeue (removing) elements.

### Operations on Queues

1. **Enqueue**: Add an element to the back of the queue.
2. **Dequeue**: Remove and return the front element from the queue.
3. **Peek**: View the front element without removing it.

## JavaScript Implementation

JavaScript doesn't have built-in implementations of stacks and queues, but you can easily create them using arrays or linked lists. Here's an example of implementing a stack and a queue using arrays:

```javascript
// Stack implementation using an array
class Stack {
  constructor() {
    this.items = [];
  }

  push(item) {
    this.items.push(item);
  }

  pop() {
    if (this.isEmpty()) {
      return null; // Stack underflow
    }
    return this.items.pop();
  }

  peek() {
    return this.items[this.items.length - 1];
  }

  isEmpty() {
    return this.items.length === 0;
  }
}

// Queue implementation using an array
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

// Usage examples
const stack = new Stack();
stack.push(1);
stack.push(2);
const topOfStack = stack.peek(); // 2
stack.pop(); // Removes and returns 2

const queue = new Queue();
queue.enqueue("A");
queue.enqueue("B");
const frontOfQueue = queue.peek(); // "A"
queue.dequeue(); // Removes and returns "A"
```