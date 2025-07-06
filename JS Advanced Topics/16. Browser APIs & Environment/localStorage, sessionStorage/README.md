# localStorage and sessionStorage

## Introduction
`localStorage` and `sessionStorage` are web storage APIs that allow developers to store key-value pairs in the browser. `localStorage` persists data across sessions, while `sessionStorage` clears data when the session ends.

## Real-Life Example
Consider a shopping cart application where the cart contents are saved in `localStorage` to persist across page reloads.

## Code Example
```javascript
// localStorage
localStorage.setItem('cart', JSON.stringify(['item1', 'item2']));
console.log(JSON.parse(localStorage.getItem('cart')));

// sessionStorage
sessionStorage.setItem('sessionData', 'temporary data');
console.log(sessionStorage.getItem('sessionData'));
```

## Problems It Solves
- Provides simple client-side storage
- Enables data persistence across sessions

## Real-Life Usage
1. **Shopping carts**: Storing cart contents.
2. **User preferences**: Saving user settings locally.

## Pros
- Easy to use
- Synchronous API

## Cons
- Limited storage capacity (5MB)
- Not suitable for sensitive data

## Conclusion
`localStorage` and `sessionStorage` are simple and effective tools for client-side storage, ideal for small amounts of non-sensitive data.
