# Test-Driven Development (TDD)

## Introduction
Test-driven development (TDD) is a software development methodology where tests are written before the actual code. This ensures that the code meets the requirements from the start.

## Real-Life Example
Consider developing a calculator app. You first write tests for addition, subtraction, etc., and then implement the logic to pass those tests.

## Code Example
```javascript
// Test
it('should add two numbers', () => {
  expect(add(2, 3)).toBe(5);
});

// Implementation
function add(a, b) {
  return a + b;
}
```

## Problems It Solves
- Reduces bugs in production
- Ensures code meets requirements

## Real-Life Usage
1. **Feature Development**: Writing tests for new features.
2. **Bug Fixing**: Writing tests to reproduce and fix bugs.

## Pros
- Improves code quality
- Encourages modular design

## Cons
- Can be time-consuming
- Requires discipline to follow

## Conclusion
TDD is a powerful methodology that ensures robust and maintainable code by focusing on testing from the start.
