# Dynamic import()

## Introduction
Dynamic `import()` is a feature in JavaScript that allows modules to be loaded dynamically at runtime. This is useful for code splitting and lazy loading.

## Real-Life Example
Consider a web application where certain features (e.g., charts, maps) are loaded only when needed. Dynamic `import()` enables this functionality.

## Code Example
```javascript
// Dynamically import a module
async function loadModule() {
  const module = await import('./module.js');
  module.default();
}

loadModule();
```

## Problems It Solves
- Reduces initial load time
- Enables lazy loading of modules

## Real-Life Usage
1. **Code splitting**: Loading modules only when required.
2. **Feature toggles**: Dynamically loading features based on user actions.

## Pros
- Improves performance
- Flexible and powerful

## Cons
- Requires modern browsers
- Can complicate debugging

## Conclusion
Dynamic `import()` is a powerful tool for optimizing JavaScript applications, enabling developers to load modules on demand.
