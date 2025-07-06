# Top-Level Await

## Introduction
Top-level `await` allows developers to use the `await` keyword outside of async functions, simplifying asynchronous code in modules.

## Real-Life Example
Consider a module that fetches configuration data from an API before exporting it.

## Code Example
```javascript
// config.js
const config = await fetch('https://api.example.com/config').then(res => res.json());
export default config;

// main.js
import config from './config.js';
console.log(config);
```

## Problems It Solves
- Simplifies asynchronous initialization in modules
- Reduces boilerplate code

## Real-Life Usage
1. **Configuration Loading**: Fetching configuration data before module usage.
2. **Data Preloading**: Preloading data for applications.

## Pros
- Simplifies async code in modules
- Reduces the need for additional async functions

## Cons
- Only works in modules
- May block module loading

## Conclusion
Top-level `await` is a powerful feature for simplifying asynchronous code in modern JavaScript modules, making it easier to write and maintain.
