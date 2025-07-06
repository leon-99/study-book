# WeakMap and WeakSet

## Introduction
WeakMap and WeakSet are advanced data structures in JavaScript that allow for weakly-referenced objects. They are useful for managing memory and avoiding memory leaks.

## Real-Life Example
Think of a temporary storage locker:
- Items (objects) are stored temporarily and removed automatically when no longer needed.

## Code Example
Using WeakMap and WeakSet:
```javascript
// Using a WeakMap
const weakMap = new WeakMap();
const obj = {};
weakMap.set(obj, 'value');
console.log(weakMap.get(obj)); // Output: value

// Using a WeakSet
const weakSet = new WeakSet();
const obj2 = {};
weakSet.add(obj2);
console.log(weakSet.has(obj2)); // Output: true
```

## Problems It Solves
- **Memory Management**: Avoids memory leaks by allowing garbage collection.
- **Temporary Storage**: Stores objects temporarily.
- **Efficient Lookups**: Provides fast access to data.

## Real-Life Usage
WeakMap and WeakSet are used in applications like caching, managing private data, and tracking object references.

## Pros and Cons
### Pros
- Prevents memory leaks.
- Supports weak references.
- Efficient for specific use cases.

### Cons
- Limited to objects as keys.
- No iteration support.

## Conclusion
WeakMap and WeakSet are specialized tools for managing memory and object references in JavaScript. By using these structures, developers can build efficient and memory-safe applications.
