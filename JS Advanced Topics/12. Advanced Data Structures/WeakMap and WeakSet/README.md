# WeakMap and WeakSet

## Introduction
`WeakMap` and `WeakSet` are advanced data structures in JavaScript that allow developers to store weakly-referenced objects. This means the objects can be garbage-collected if there are no other references to them.

## Real-Life Example
Consider a caching system where you want to store metadata for DOM elements without preventing them from being garbage-collected. `WeakMap` is ideal for this use case.

## Code Example
```javascript
// WeakMap example
const weakMap = new WeakMap();
const element = document.createElement('div');
weakMap.set(element, { id: 1 });
console.log(weakMap.get(element)); // { id: 1 }

// WeakSet example
const weakSet = new WeakSet();
const obj = {};
weakSet.add(obj);
console.log(weakSet.has(obj)); // true
```

## Problems It Solves
- Prevents memory leaks
- Enables efficient storage of metadata

## Real-Life Usage
1. **DOM metadata**: Storing metadata for DOM elements.
2. **Caching**: Implementing weakly-referenced caches.

## Pros
- Prevents memory leaks
- Efficient and lightweight

## Cons
- Limited API
- Only works with objects

## Conclusion
`WeakMap` and `WeakSet` are specialized data structures that provide unique solutions for managing weakly-referenced objects, making them valuable tools in certain scenarios.
