# Mocking and Stubbing

## Introduction
Mocking and stubbing are techniques used in testing to simulate the behavior of real objects or functions. These techniques are essential for isolating components and testing them in controlled environments.

## Real-Life Example
Think of a flight simulator:
- Pilots practice flying without using a real airplane.

## Code Example
Using Jest for mocking:
```javascript
// userService.js
const fetchUser = (id) => {
  // Simulate an API call
  return { id, name: 'John Doe' };
};
module.exports = fetchUser;

// userService.test.js
const fetchUser = require('./userService');

jest.mock('./userService', () => jest.fn());

test('fetchUser returns mocked data', () => {
  fetchUser.mockReturnValue({ id: 1, name: 'Mocked User' });
  const user = fetchUser(1);
  expect(user.name).toBe('Mocked User');
});
```

## Problems It Solves
- **Isolation**: Tests components without dependencies.
- **Control**: Simulates specific scenarios.
- **Efficiency**: Reduces test execution time.

## Real-Life Usage
Mocking and stubbing are used in testing to isolate components and simulate external dependencies like APIs or databases.

## Pros and Cons
### Pros
- Simplifies testing.
- Isolates components.
- Reduces test execution time.

### Cons
- May not reflect real-world scenarios.
- Requires additional setup.

## Conclusion
Mocking and stubbing are powerful techniques for isolating components and testing them in controlled environments. By using these techniques, developers can write efficient and reliable tests.
