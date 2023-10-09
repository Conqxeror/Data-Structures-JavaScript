# Binary Search Tree (BST) in JavaScript

A Binary Search Tree (BST) is a binary tree with the property that the value of each node is greater than or equal to the values of its left children and less than or equal to the values of its right children. BSTs are used to efficiently store and search for data in sorted order.

## Operations on Binary Search Trees

Common operations on BSTs include:

- **Insertion**: Adding a new value to the BST while maintaining the BST property.
- **Deletion**: Removing a node with a specific value from the BST while preserving the BST property.
- **Searching**: Finding a node with a specific value in the BST.
- **Traversal**: Visiting nodes in a specific order (in-order, pre-order, or post-order).
- **Minimum and Maximum**: Finding the minimum and maximum values in the BST.

## Advantages of Binary Search Trees

- Efficient searching: BSTs provide efficient searching for specific values.
- Sorting: BSTs can be used to sort data as elements are inserted.
- Balanced BSTs (e.g., AVL trees) maintain balanced structures for faster operations.

## JavaScript Implementation

In JavaScript, you can implement a binary search tree using classes and objects. Here's an example of implementing a basic binary search tree:

```javascript
class TreeNode {
  constructor(value) {
    this.value = value;
    this.left = null;
    this.right = null;
  }
}

class BinarySearchTree {
  constructor() {
    this.root = null;
  }

  // Insert a new value into the BST
  insert(value) {
    const newNode = new TreeNode(value);
    if (!this.root) {
      this.root = newNode;
    } else {
      this._insertNode(this.root, newNode);
    }
  }

  _insertNode(node, newNode) {
    if (newNode.value < node.value) {
      if (!node.left) {
        node.left = newNode;
      } else {
        this._insertNode(node.left, newNode);
      }
    } else {
      if (!node.right) {
        node.right = newNode;
      } else {
        this._insertNode(node.right, newNode);
      }
    }
  }

  // Other methods like search, traversal, and deletion can be implemented here
}

// Usage example
const bst = new BinarySearchTree();
bst.insert(5);
bst.insert(3);
bst.insert(7);
```