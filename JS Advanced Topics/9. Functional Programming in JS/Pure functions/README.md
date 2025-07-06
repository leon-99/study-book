# Pure Functions

## Introduction
A pure function is a function that, given the same input, always returns the same output and has no side effects. Pure functions are a cornerstone of functional programming.

## Real-Life Example
Consider a function that calculates the area of a rectangle. It always returns the same result for the same width and height, without modifying any external state.

## Code Example
```javascript
function calculateArea(width, height) {
  return width * height;
}

console.log(calculateArea(5, 10)); // 50
```

## Problems It Solves
- Simplifies testing
- Enhances code predictability

## Real-Life Usage
1. **Mathematical calculations**: Functions for calculations are often pure.
2. **State management**: Pure functions are used in reducers for state updates.

## Pros
- Easy to test and debug
- Promotes code reliability

## Cons
- May require additional parameters
- Can lead to verbose code

## Conclusion
Pure functions are a fundamental concept in functional programming, enabling developers to write predictable and maintainable code.
