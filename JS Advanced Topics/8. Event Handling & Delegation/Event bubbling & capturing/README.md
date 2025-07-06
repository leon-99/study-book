# Event Bubbling & Capturing

## Introduction
Event bubbling and capturing are two phases of event propagation in the DOM. Bubbling starts from the target element and propagates upwards, while capturing starts from the root and propagates downwards.

## Real-Life Example
Imagine clicking a button inside a form. The click event can propagate to the form and then to the document, allowing different levels to handle the event.

## Code Example
```javascript
const button = document.querySelector('button');
const form = document.querySelector('form');

document.addEventListener('click', () => {
  console.log('Document clicked');
}, true); // Capturing phase

form.addEventListener('click', () => {
  console.log('Form clicked');
}); // Bubbling phase

button.addEventListener('click', () => {
  console.log('Button clicked');
});
```

## Problems It Solves
- Enables hierarchical event handling
- Allows multiple levels to respond to the same event

## Real-Life Usage
1. **Form validation**: Handling events at the form level.
2. **Global event listeners**: Capturing events at the document level.

## Pros
- Flexible event handling
- Supports complex UI interactions

## Cons
- Can lead to unexpected behavior if not understood
- Debugging can be challenging

## Conclusion
Understanding event bubbling and capturing is essential for effective event handling in JavaScript, enabling developers to build interactive and responsive applications.
