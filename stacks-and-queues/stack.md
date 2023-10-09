# Stack in JavaScript

A stack is a linear data structure that follows the Last-In-First-Out (LIFO) principle. In a stack, the last item added is the first one to be removed. Stacks are used to manage collections of elements where you need to maintain order and perform operations like pushing (adding) and popping (removing) elements.

## Operations on Stacks

1. **Push**: Add an element to the top of the stack.
2. **Pop**: Remove and return the top element from the stack.
3. **Peek**: View the top element without removing it.

## Common Use Cases

Stacks are used in various scenarios, including but not limited to:

- Function call stack: Keeping track of function calls and their return addresses.
- Undo/redo functionality in applications.
- Expression evaluation (e.g., checking balanced parentheses in an expression).
- Backtracking algorithms (e.g., depth-first search in graphs).

## JavaScript Implementation

In JavaScript, you can implement a stack using arrays or linked lists. Here's an example of implementing a stack using an array:

```javascript
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

// Usage example
const stack = new Stack();
stack.push(1);
stack.push(2);
const topOfStack = stack.peek(); // 2
stack.pop(); // Removes and returns 2
