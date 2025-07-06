# Map, Reduce, Filter, Compose, and Pipe

## Introduction
`map`, `reduce`, and `filter` are array methods in JavaScript that enable functional programming. `compose` and `pipe` are techniques for combining functions to create more complex operations.

## Real-Life Example
Consider a scenario where you need to process a list of numbers by filtering out odd numbers, doubling the even numbers, and summing them up.

## Code Example
```javascript
const numbers = [1, 2, 3, 4, 5];

const result = numbers
  .filter((n) => n % 2 === 0)
  .map((n) => n * 2)
  .reduce((sum, n) => sum + n, 0);

console.log(result); // 12

// Compose and Pipe
const compose = (...fns) => (x) => fns.reduceRight((v, f) => f(v), x);
const pipe = (...fns) => (x) => fns.reduce((v, f) => f(v), x);

const add = (x) => x + 1;
const multiply = (x) => x * 2;

const composed = compose(multiply, add);
const piped = pipe(add, multiply);

console.log(composed(5)); // 12
console.log(piped(5)); // 12
```

## Problems It Solves
- Simplifies array transformations
- Enhances function composition

## Real-Life Usage
1. **Data processing**: Transforming and aggregating data.
2. **Functional pipelines**: Creating reusable data processing pipelines.

## Pros
- Improves code readability
- Encourages modular design

## Cons
- Can be confusing for beginners
- May introduce performance overhead

## Conclusion
`map`, `reduce`, `filter`, `compose`, and `pipe` are essential tools in functional programming, enabling developers to write clean and efficient code.
