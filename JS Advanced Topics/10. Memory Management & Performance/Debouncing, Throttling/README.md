# Debouncing and Throttling

## Introduction
Debouncing and throttling are techniques used to control the rate at which a function is executed, improving performance in scenarios like event handling.

## Real-Life Example
Imagine a search bar that fetches results as the user types. Debouncing ensures the fetch function is called only after the user stops typing, while throttling limits the number of fetch calls per second.

## Code Example
```javascript
// Debouncing
function debounce(func, delay) {
  let timer;
  return function (...args) {
    clearTimeout(timer);
    timer = setTimeout(() => func.apply(this, args), delay);
  };
}

const debouncedSearch = debounce(() => console.log('Fetching results...'), 300);
window.addEventListener('input', debouncedSearch);

// Throttling
function throttle(func, limit) {
  let lastFunc;
  let lastRan;
  return function (...args) {
    const context = this;
    if (!lastRan) {
      func.apply(context, args);
      lastRan = Date.now();
    } else {
      clearTimeout(lastFunc);
      lastFunc = setTimeout(() => {
        if (Date.now() - lastRan >= limit) {
          func.apply(context, args);
          lastRan = Date.now();
        }
      }, limit - (Date.now() - lastRan));
    }
  };
}

const throttledScroll = throttle(() => console.log('Scrolling...'), 200);
window.addEventListener('scroll', throttledScroll);
```

## Problems It Solves
- Reduces unnecessary function calls
- Improves application performance

## Real-Life Usage
1. **Search bars**: Debouncing input events.
2. **Scroll events**: Throttling scroll handlers.

## Pros
- Enhances performance
- Reduces resource usage

## Cons
- Adds complexity to code
- Requires careful tuning of delay/limit

## Conclusion
Debouncing and throttling are essential techniques for optimizing event-driven applications, ensuring smooth and efficient performance.
