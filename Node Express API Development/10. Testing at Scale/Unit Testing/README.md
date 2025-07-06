# Unit Testing

## Introduction
Unit testing involves testing individual components or functions of an application in isolation. It ensures that each unit of the codebase works as expected.

## Real-Life Example
Think of a car:
- Each part (e.g., engine, brakes) is tested individually to ensure it functions correctly.

## Code Example
Using Jest for unit testing:
```javascript
// math.js
function add(a, b) {
  return a + b;
}
module.exports = add;

// math.test.js
const add = require('./math');

test('adds 1 + 2 to equal 3', () => {
  expect(add(1, 2)).toBe(3);
});
```

## Problems It Solves
- **Code Quality**: Ensures individual components work as intended.
- **Bug Detection**: Identifies issues early in the development process.
- **Documentation**: Serves as a form of documentation for the codebase.

## Real-Life Usage
Unit testing is widely used in software development to ensure code reliability and maintainability.

## Pros and Cons
### Pros
- Fast and efficient.
- Easy to write and maintain.
- Provides immediate feedback.

### Cons
- Limited to individual components.
- May not catch integration issues.

## Conclusion
Unit testing is a fundamental practice for ensuring code quality. By writing unit tests, developers can build reliable and maintainable applications.
