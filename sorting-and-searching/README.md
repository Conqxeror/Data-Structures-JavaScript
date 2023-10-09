# Sorting and Searching Algorithms in JavaScript

Sorting and searching are fundamental operations in computer science and are widely used in various applications. Sorting algorithms arrange elements in a specific order, while searching algorithms find a target value within a collection of data.

## Sorting Algorithms

Sorting algorithms are used to order elements in a collection, making it easier to search for specific items or process data efficiently. Common sorting algorithms include:

- **Bubble Sort**: Repeatedly steps through the list, compares adjacent elements, and swaps them if they are in the wrong order.
- **Quick Sort**: A divide-and-conquer algorithm that divides the array into smaller subarrays and sorts them.
- **Merge Sort**: Another divide-and-conquer algorithm that divides the array into two halves, sorts them, and merges them back together.
- **Insertion Sort**: Builds the sorted array one item at a time by repeatedly inserting the next element in the correct position.
- **Selection Sort**: Repeatedly selects the minimum element from the unsorted part of the array and puts it in the sorted part.

## Searching Algorithms

Searching algorithms are used to find a specific value or item within a collection of data. Common searching algorithms include:

- **Linear Search**: Iterates through each element in the collection until it finds the target value.
- **Binary Search**: Applies to sorted collections and repeatedly divides the search interval in half.
- **Hashing**: Uses a hash function to map keys to values in a data structure like a hash table.
- **Depth-First Search (DFS)**: Explores as far as possible along each branch before backtracking (used in graph traversal).

## JavaScript Implementation

In JavaScript, you can implement these sorting and searching algorithms for various data structures, such as arrays and trees. Here's an example of implementing the Quick Sort algorithm:

```js
function quickSort(arr) {
  if (arr.length <= 1) {
    return arr;
  }

  const pivot = arr[0];
  const left = [];
  const right = [];

  for (let i = 1; i < arr.length; i++) {
    if (arr[i] < pivot) {
      left.push(arr[i]);
    } else {
      right.push(arr[i]);
    }
  }

  return [...quickSort(left), pivot, ...quickSort(right)];
}

// Usage example
const unsortedArray = [5, 3, 7, 2, 8, 4];
const sortedArray = quickSort(unsortedArray);
```