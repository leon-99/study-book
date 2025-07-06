# Unit Testing with Jest and Mocha

## Introduction
Unit testing involves testing individual units or components of a software application in isolation. Jest and Mocha are popular frameworks for unit testing in JavaScript.

## Real-Life Example
Testing a utility function that formats dates to ensure it works correctly for all inputs.

## Code Example
```javascript
// Function to test
function formatDate(date) {
  return date.toISOString().split('T')[0];
}

// Jest Test
it('should format date correctly', () => {
  const date = new Date('2025-07-06');
  expect(formatDate(date)).toBe('2025-07-06');
});

// Mocha Test
const assert = require('assert');
describe('formatDate', () => {
  it('should format date correctly', () => {
    const date = new Date('2025-07-06');
    assert.strictEqual(formatDate(date), '2025-07-06');
  });
});
```

## Problems It Solves
- Ensures individual components work as expected
- Simplifies debugging by isolating issues

## Real-Life Usage
1. **Utility Functions**: Testing helper functions.
2. **Component Testing**: Verifying React/Vue components.

## Pros
- Improves code quality
- Provides quick feedback during development

## Cons
- Requires time to write tests
- May not cover integration issues

## Conclusion
Unit testing with Jest and Mocha is a fundamental practice for ensuring the reliability and maintainability of software applications.
