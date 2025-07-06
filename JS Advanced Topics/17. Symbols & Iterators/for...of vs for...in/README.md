# for...of vs for...in

## Introduction
The `for...of` and `for...in` loops in JavaScript are used for iteration, but they serve different purposes. `for...of` iterates over iterable objects like arrays, while `for...in` iterates over enumerable properties of an object.

## Real-Life Example
Consider an array of items and an object with key-value pairs. Choosing the appropriate loop depends on the data structure.

## Code Example
```javascript
// for...of example
const items = ['item1', 'item2', 'item3'];
for (const item of items) {
  console.log(item);
}

// for...in example
const obj = { a: 1, b: 2, c: 3 };
for (const key in obj) {
  console.log(key, obj[key]);
}
```

## Problems It Solves
- Simplifies iteration over arrays and objects
- Provides clear semantics for different use cases

## Real-Life Usage
1. **Arrays**: Using `for...of` for array iteration.
2. **Objects**: Using `for...in` for object property iteration.

## Pros
- `for...of` is concise and works with iterables
- `for...in` is useful for object properties

## Cons
- `for...in` includes inherited properties
- `for...of` requires an iterable object

## Conclusion
Understanding the differences between `for...of` and `for...in` is essential for choosing the right loop for the task, ensuring clear and efficient code.
