# addEventListener Options

## Introduction
The `addEventListener` method in JavaScript allows developers to attach event listeners to DOM elements. It also provides options to control the behavior of the event listener, such as `capture`, `once`, and `passive`.

## Real-Life Example
Imagine a button that should only respond to a click event once. Using the `once` option, you can ensure the event listener is automatically removed after the first execution.

## Code Example
```javascript
const button = document.querySelector('button');

button.addEventListener('click', () => {
  console.log('Button clicked!');
}, { once: true });

// The event listener will be removed after the first click.
```

## Problems It Solves
- Fine-grained control over event listeners
- Prevents memory leaks by automatically removing listeners

## Real-Life Usage
1. **Single-use events**: Using the `once` option for events that should only trigger once.
2. **Performance optimization**: Using the `passive` option for scroll events to improve performance.

## Pros
- Flexible and powerful
- Reduces boilerplate code

## Cons
- Requires understanding of options
- Not supported in very old browsers

## Conclusion
The `addEventListener` options provide developers with powerful tools to manage event listeners effectively, improving both performance and maintainability.
