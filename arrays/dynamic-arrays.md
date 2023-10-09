# Dynamic Arrays in JavaScript

A dynamic array, often referred to as a dynamic array list or simply an ArrayList, is an array that automatically resizes itself when it runs out of space. In JavaScript, dynamic arrays are commonly implemented using the built-in array data structure.

## Advantages of Dynamic Arrays

- Dynamic resizing: Dynamic arrays can grow or shrink as needed, making them versatile.
- Random access: You can access elements by their index efficiently.
- Efficient insertion and deletion: Appending and removing elements are generally efficient.

## JavaScript Implementation

In JavaScript, the built-in array can be considered a dynamic array because it automatically resizes when necessary. Here's an example of working with dynamic arrays:

```javascript
// Creating an empty array
const dynamicArray = [];

// Adding elements to the array
dynamicArray.push(1);
dynamicArray.push(2);
dynamicArray.push(3);

// Accessing elements by index
const secondElement = dynamicArray[1]; // 2

// Removing an element by value
const indexToRemove = dynamicArray.indexOf(2);
if (indexToRemove !== -1) {
  dynamicArray.splice(indexToRemove, 1);
}

// Dynamic resizing happens behind the scenes as you add or remove elements

// Iterating through the dynamic array
for (const element of dynamicArray) {
  console.log(element);
}
```