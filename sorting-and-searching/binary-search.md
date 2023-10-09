# Binary Search in JavaScript

Binary Search is a fast and efficient search algorithm used to find a specific target value within a sorted collection of data. It works by repeatedly dividing the search interval in half until the target value is found or the interval is empty.

## How Binary Search Works

1. Start with the entire sorted collection.
2. Calculate the middle index of the current interval.
3. Compare the middle element with the target value.
   - If they are equal, the search is successful.
   - If the middle element is greater than the target, search the left half.
   - If the middle element is less than the target, search the right half.
4. Repeat steps 2 and 3 until the target is found or the interval is empty.

## JavaScript Implementation

Here's an example of implementing the Binary Search algorithm in JavaScript:

```javascript
function binarySearch(sortedArray, target) {
  let left = 0;
  let right = sortedArray.length - 1;

  while (left <= right) {
    const mid = Math.floor((left + right) / 2);

    if (sortedArray[mid] === target) {
      return mid; // Found the target at index 'mid'
    } else if (sortedArray[mid] < target) {
      left = mid + 1; // Search the right half
    } else {
      right = mid - 1; // Search the left half
    }
  }

  return -1; // Target not found
}

// Usage example
const sortedArray = [2, 3, 4, 5, 7, 8, 10, 12];
const target = 7;
const index = binarySearch(sortedArray, target);
 