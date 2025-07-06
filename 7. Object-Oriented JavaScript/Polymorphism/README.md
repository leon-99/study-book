# Polymorphism

## Introduction
Polymorphism is a core concept in object-oriented programming that allows objects to be treated as instances of their parent class, enabling a single interface to represent different types.

## Real-Life Example
Consider a payment system where different payment methods (e.g., credit card, PayPal, bank transfer) share a common interface but have unique implementations.

## Code Example
```javascript
class Payment {
  process() {
    console.log("Processing payment");
  }
}

class CreditCardPayment extends Payment {
  process() {
    console.log("Processing credit card payment");
  }
}

class PayPalPayment extends Payment {
  process() {
    console.log("Processing PayPal payment");
  }
}

function processPayment(payment) {
  payment.process();
}

const payment1 = new CreditCardPayment();
const payment2 = new PayPalPayment();

processPayment(payment1); // Processing credit card payment
processPayment(payment2); // Processing PayPal payment
```

## Problems It Solves
- Code reusability
- Simplifies interface design
- Enhances flexibility

## Real-Life Usage
Polymorphism is widely used in frameworks and libraries to provide extensible and reusable components.

## Pros
- Promotes code reuse
- Simplifies maintenance

## Cons
- Can lead to complexity if overused
- Requires careful design

## Conclusion
Polymorphism is a powerful concept in object-oriented programming, enabling flexible and reusable code.
