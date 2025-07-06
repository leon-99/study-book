# ES Modules (import - export)

## Introduction
ES Modules (ESM) is the official JavaScript module system introduced in ES6. It allows developers to use `import` and `export` statements for modular code.

## Real-Life Example
Consider a web application with separate files for user authentication, data fetching, and UI components. ESM enables you to import only the required functionalities.

## Code Example
```javascript
// auth.js
export function login(user) {
  console.log(`${user} logged in`);
}

// app.js
import { login } from "./auth.js";
login("John");
```

## Problems It Solves
- Standardized module system
- Better browser compatibility
- Tree-shaking for optimized builds

## Real-Life Usage
ESM is used in modern JavaScript frameworks like React, Angular, and Vue.

## Pros
- Native support in modern browsers
- Asynchronous loading

## Cons
- Requires transpilation for older browsers
- Slightly more complex setup compared to CommonJS

## Conclusion
ES Modules provide a standardized and efficient way to manage dependencies in modern JavaScript applications.
