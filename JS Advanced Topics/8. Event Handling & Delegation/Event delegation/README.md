# Event Delegation

## Introduction
Event delegation is a technique in JavaScript where a single event listener is attached to a parent element to handle events for its child elements. This is achieved using event propagation.

## Real-Life Example
Consider a list of items where clicking on any item should trigger an action. Instead of adding event listeners to each item, you can add a single listener to the parent element.

## Code Example
```javascript
const list = document.querySelector('ul');

list.addEventListener('click', (event) => {
  if (event.target.tagName === 'LI') {
    console.log(`Item clicked: ${event.target.textContent}`);
  }
});
```

## Problems It Solves
- Reduces memory usage by minimizing event listeners
- Simplifies dynamic element handling

## Real-Life Usage
1. **Dynamic lists**: Handling events for dynamically added list items.
2. **Performance optimization**: Reducing the number of event listeners in large applications.

## Pros
- Efficient and scalable
- Simplifies event management

## Cons
- Requires understanding of event propagation
- Limited to certain use cases

## Conclusion
Event delegation is a powerful technique for efficient event handling, especially in applications with dynamic or large DOM structures.
