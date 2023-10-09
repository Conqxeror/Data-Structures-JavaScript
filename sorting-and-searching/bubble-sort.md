# Bubble Sort in JavaScript

Bubble Sort is a simple sorting algorithm that repeatedly steps through the list, compares adjacent elements, and swaps them if they are in the wrong order. The pass through the list is repeated until no swaps are needed, indicating that the list is sorted.

## How Bubble Sort Works

1. Start from the beginning of the array.
2. Compare adjacent elements (e.g., `arr[i]` and `arr[i+1]`).
3. If `arr[i]` is greater than `arr[i+1]`, swap the two elements.
4. Repeat steps 2 and 3 for each pair of adjacent elements throughout the array.
5. After the first pass, the largest element will have "bubbled up" to the end of the array.
6. Repeat steps 1-5 for the remaining elements (excluding the already sorted ones).
7. Continue this process until no swaps are needed.

## JavaScript Implementation

Here's an example of implementing the Bubble Sort algorithm in JavaScript:

```javascript
function bubbleSort(arr) {
  const n = arr.length;
  let swapped;
  
  do {
    swapped = false;
    for (let i = 0; i < n - 1; i++) {
      if (arr[i] > arr[i + 1]) {
        // Swap arr[i] and arr[i+1]
        const temp = arr[i];
        arr[i] = arr[i + 1];
        arr[i + 1] = temp;
        swapped = true;
      }
    }
  } while (swapped);

  return arr;
}

// Usage example
const unsortedArray = [5, 3, 7, 2, 8, 4];
const sortedArray = bubbleSort(unsortedArray);
