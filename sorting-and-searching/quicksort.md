# Quick Sort in JavaScript

Quick Sort is a highly efficient, divide-and-conquer sorting algorithm. It works by selecting a 'pivot' element from the array and partitioning the other elements into two sub-arrays, according to whether they are less than or greater than the pivot. The sub-arrays are then sorted recursively.

## How Quick Sort Works

1. Choose a 'pivot' element from the array.
2. Partition the array into two sub-arrays: elements less than the pivot and elements greater than the pivot.
3. Recursively sort the sub-arrays.
4. Combine the sub-arrays and pivot into a single sorted array.

## JavaScript Implementation

Here's an example of implementing the Quick Sort algorithm in JavaScript:

```javascript
function quickSort(arr) {
  if (arr.length <= 1) {
    return arr;
  }

  const pivot = arr[Math.floor(arr.length / 2)];
  const left = [];
  const right = [];

  for (const element of arr) {
    if (element < pivot) {
      left.push(element);
    } else if (element > pivot) {
      right.push(element);
    }
  }

  return [...quickSort(left), pivot, ...quickSort(right)];
}

// Usage example
const unsortedArray = [5, 3, 7, 2, 8, 4];
const sortedArray = quickSort(unsortedArray);
```