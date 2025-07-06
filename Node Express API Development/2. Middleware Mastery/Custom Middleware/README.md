# Custom Middleware

## Introduction
Middleware in Express.js is a function that has access to the request and response objects, and the next middleware function in the application’s request-response cycle. Custom middleware allows developers to implement specific logic, such as logging, authentication, or request validation.

## Real-Life Example
Think of a security checkpoint at an airport:
- The checkpoint (middleware) inspects passengers (requests) before they proceed to the boarding gate (next middleware or route handler).

## Code Example
```javascript
// Custom middleware for logging
const loggerMiddleware = (req, res, next) => {
  console.log(`${req.method} ${req.url}`);
  next(); // Pass control to the next middleware
};

// Using the middleware in an Express app
const express = require('express');
const app = express();

app.use(loggerMiddleware);

app.get('/', (req, res) => {
  res.send('Hello, World!');
});

app.listen(3000, () => console.log('Server running on port 3000'));
```

## Problems It Solves
- **Reusability**: Encapsulates logic that can be reused across routes.
- **Modularity**: Keeps route handlers clean and focused.
- **Flexibility**: Allows chaining of multiple middleware functions.

## Real-Life Usage
Custom middleware is widely used for tasks like logging, authentication, input validation, and error handling in web applications.

## Pros and Cons
### Pros
- Promotes code reuse and modularity.
- Simplifies route handlers.
- Provides flexibility in request handling.

### Cons
- Can lead to complex middleware chains.
- Improper error handling can break the chain.

## Conclusion
Custom middleware is a powerful feature of Express.js that enables developers to implement reusable and modular logic. By leveraging middleware, applications can be made more maintainable and scalable.
