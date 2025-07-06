# IIFEs (Immediately Invoked Function Expressions)

## Introduction
An IIFE (Immediately Invoked Function Expression) is a JavaScript function that runs as soon as it is defined. It is often used to create a private scope and avoid polluting the global namespace.

## Real-Life Example
Consider a scenario where you need to initialize a module without exposing its internal variables to the global scope.

## Code Example
```javascript
(function () {
  const privateVar = "I am private";
  console.log(privateVar);
})();

// privateVar is not accessible here
```

## Problems It Solves
- Avoids global namespace pollution
- Creates private scopes

## Real-Life Usage
1. **Module initialization**: Encapsulating initialization logic.
2. **Legacy code**: Managing global variables in older codebases.

## Pros
- Simple and effective
- Reduces global variable conflicts

## Cons
- Limited to specific use cases
- Can be less readable for beginners

## Conclusion
IIFEs are a useful pattern for creating private scopes and avoiding global namespace pollution, especially in older JavaScript codebases.
