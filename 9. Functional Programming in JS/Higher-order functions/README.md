# Higher-Order Functions

## Introduction
Higher-order functions are functions that take other functions as arguments or return functions as their result. They are a cornerstone of functional programming, enabling abstraction and code reuse.

## Real-Life Example
Consider a scenario where you need to apply a discount to a list of prices. A higher-order function can abstract the discount logic.

## Code Example
```javascript
function applyDiscount(discount) {
  return function (price) {
    return price - price * discount;
  };
}

const tenPercentOff = applyDiscount(0.1);
console.log(tenPercentOff(100)); // 90
```

## Problems It Solves
- Reduces code duplication
- Enhances abstraction

## Real-Life Usage
1. **Array methods**: Methods like `map`, `filter`, and `reduce` are higher-order functions.
2. **Event handling**: Passing callback functions to event listeners.

## Pros
- Promotes code reuse
- Simplifies complex logic

## Cons
- Can be harder to debug
- May introduce performance overhead

## Conclusion
Higher-order functions are a fundamental concept in functional programming, enabling developers to write more abstract and reusable code.
