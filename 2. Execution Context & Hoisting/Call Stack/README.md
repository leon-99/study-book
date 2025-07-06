# Call Stack

## Introduction
The call stack is a data structure that keeps track of function calls in JavaScript. It follows the Last In, First Out (LIFO) principle, meaning the last function added to the stack is the first one to be executed.

## Real-Life Example
Imagine a stack of plates. You can only add or remove plates from the top of the stack. Similarly, the call stack adds and removes function calls in a specific order.

### Code Example
```javascript
function first() {
    console.log('First function');
}

function second() {
    console.log('Second function');
    first();
}

function third() {
    console.log('Third function');
    second();
}

third();
// Output:
// Third function
// Second function
// First function
```

## Problems It Solves
1. **Execution Order**: Ensures functions are executed in the correct order.
2. **Error Tracking**: Helps in identifying the source of errors through stack traces.

## Real-Life Usage
1. **Debugging**: Developers use the call stack to trace errors and understand execution flow.
   ```javascript
   function buggyFunction() {
       throw new Error('Something went wrong');
   }

   try {
       buggyFunction();
   } catch (error) {
       console.error(error.stack);
   }
   ```

2. **Nested Function Calls**: The call stack manages nested function calls efficiently.
   ```javascript
   function outer() {
       function inner() {
           console.log('Inner function');
       }
       inner();
   }

   outer();
   ```

## Pros
- **Orderly Execution**: Maintains a clear execution order.
- **Error Tracking**: Provides detailed stack traces for debugging.

## Cons
- **Stack Overflow**: Too many nested calls can lead to stack overflow errors.
- **Limited Size**: The call stack has a finite size, which can be a limitation for deeply recursive functions.

## Conclusion
The call stack is a fundamental concept in JavaScript. Understanding how it works is essential for debugging and writing efficient code.