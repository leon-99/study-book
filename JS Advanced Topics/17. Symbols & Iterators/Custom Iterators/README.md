# Custom Iterators

## Introduction
Custom iterators in JavaScript allow developers to define how an object should be iterated. This is achieved by implementing the `Symbol.iterator` method.

## Real-Life Example
Consider a collection of tasks where each task needs to be processed sequentially. A custom iterator can define the order of iteration.

## Code Example
```javascript
const tasks = {
  items: ['Task 1', 'Task 2', 'Task 3'],
  [Symbol.iterator]() {
    let index = 0;
    const items = this.items;
    return {
      next() {
        if (index < items.length) {
          return { value: items[index++], done: false };
        } else {
          return { done: true };
        }
      },
    };
  },
};

for (const task of tasks) {
  console.log(task);
}
```

## Problems It Solves
- Provides custom iteration logic
- Enables iteration over non-array objects

## Real-Life Usage
1. **Data processing**: Iterating over custom data structures.
2. **Custom collections**: Defining iteration logic for collections.

## Pros
- Highly flexible
- Integrates with `for...of` and other iteration constructs

## Cons
- Requires additional code
- Can be complex to implement

## Conclusion
Custom iterators are a powerful feature for defining iteration logic, enabling developers to work with non-standard data structures in a consistent way.
