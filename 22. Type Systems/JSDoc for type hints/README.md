# JSDoc for Type Hints

## Introduction
JSDoc is a documentation generator for JavaScript that also supports type annotations, enabling basic type checking and IDE support.

## Real-Life Example
Consider a project where lightweight type annotations are needed without introducing a full type system like TypeScript.

## Code Example
```javascript
/**
 * Adds two numbers.
 * @param {number} a - The first number.
 * @param {number} b - The second number.
 * @returns {number} The sum of the two numbers.
 */
function add(a, b) {
  return a + b;
}

add('2', 3); // Warning: Argument of type 'string' is not assignable to parameter of type 'number'.
```

## Problems It Solves
- Provides lightweight type checking
- Improves IDE support and documentation

## Real-Life Usage
1. **Small Projects**: Adding type hints without a full type system.
2. **Library Development**: Documenting APIs with type annotations.

## Pros
- Easy to adopt
- Improves code readability and documentation

## Cons
- Limited type checking capabilities
- No deep integration like TypeScript

## Conclusion
JSDoc is a simple and effective way to add type hints and improve documentation in JavaScript projects.
