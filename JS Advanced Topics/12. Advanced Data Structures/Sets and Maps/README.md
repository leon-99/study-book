# Sets and Maps

## Introduction
`Set` and `Map` are advanced data structures in JavaScript. `Set` is used to store unique values, while `Map` is used to store key-value pairs with better performance and flexibility compared to plain objects.

## Real-Life Example
Imagine a contact list where each contact must be unique. A `Set` can ensure no duplicate entries.

## Code Example
```javascript
// Set example
const uniqueNumbers = new Set([1, 2, 3, 3]);
console.log(uniqueNumbers); // Set { 1, 2, 3 }

// Map example
const phoneBook = new Map();
phoneBook.set('Alice', '123-456-7890');
phoneBook.set('Bob', '987-654-3210');
console.log(phoneBook.get('Alice')); // 123-456-7890
```

## Problems It Solves
- Ensures uniqueness with `Set`
- Efficient key-value storage with `Map`

## Real-Life Usage
1. **Data deduplication**: Using `Set` to remove duplicates.
2. **Key-value storage**: Using `Map` for efficient lookups.

## Pros
- Flexible and efficient
- Built-in methods for common operations

## Cons
- Limited to specific use cases
- Slightly more complex than arrays and objects

## Conclusion
`Set` and `Map` are versatile data structures that provide unique solutions for specific problems, making them essential tools in modern JavaScript development.
