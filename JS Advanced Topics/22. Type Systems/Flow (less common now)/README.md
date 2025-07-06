# Flow (Less Common Now)

## Introduction
Flow is a static type checker for JavaScript, developed by Facebook, that helps catch type-related errors during development.

## Real-Life Example
Consider a project where strict type checking is required to prevent runtime errors, such as a large-scale web application.

## Code Example
```javascript
// @flow
function square(n: number): number {
  return n * n;
}

square('2'); // Error: string is not assignable to number
```

## Problems It Solves
- Catches type-related errors early
- Improves code reliability

## Real-Life Usage
1. **Web Applications**: Ensuring type safety in large projects.
2. **Library Development**: Providing type definitions for users.

## Pros
- Integrates well with existing JavaScript code
- Provides early error detection

## Cons
- Less popular compared to TypeScript
- Requires additional setup

## Conclusion
While Flow is less commonly used now, it remains a useful tool for projects that require static type checking in JavaScript.
