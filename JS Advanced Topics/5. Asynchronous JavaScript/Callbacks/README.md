## Introduction
Callbacks are one of the fundamental concepts in JavaScript for handling asynchronous operations. A callback is a function passed as an argument to another function, which is then executed after the completion of the operation.

## Real-Life Example
Imagine ordering food at a restaurant. You place your order (function call) and wait for the server to bring your food (callback function). The server notifies you when your food is ready.

### Code Example
```javascript
function fetchData(callback) {
    setTimeout(() => {
        console.log('Data fetched');
        callback();
    }, 2000);
}

function processData() {
    console.log('Processing data');
}

fetchData(processData);
```

## Problems It Solves
1. **Asynchronous Execution**: Allows non-blocking operations.
2. **Event Handling**: Provides a way to handle events asynchronously.

## Real-Life Usage
1. **Event Listeners**: Handling user interactions.
   ```javascript
   document.querySelector('button').addEventListener('click', () => {
       console.log('Button clicked');
   });
   ```

2. **API Calls**: Fetching data from a server.

## Pros
- **Simplicity**: Easy to understand and use.
- **Flexibility**: Can be used in various scenarios.

## Cons
- **Callback Hell**: Nested callbacks can make code hard to read and maintain.
- **Error Handling**: Requires explicit error handling.

## Conclusion
Callbacks are a powerful tool for handling asynchronous operations in JavaScript. By understanding how they work, developers can write more efficient and responsive code.
