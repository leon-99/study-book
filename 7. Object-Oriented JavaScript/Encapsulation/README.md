## Introduction
Encapsulation in JavaScript is the practice of bundling data and methods that operate on that data within a single unit, such as a class or object. It also involves restricting direct access to some of the object's components.

## Real-Life Example
Think of a bank account. You can deposit or withdraw money (methods), but you cannot directly access the account balance (private data).

### Code Example
```javascript
class BankAccount {
    #balance; // Private field

    constructor(initialBalance) {
        this.#balance = initialBalance;
    }

    deposit(amount) {
        this.#balance += amount;
        console.log(`Deposited: ${amount}`);
    }

    getBalance() {
        return this.#balance;
    }
}

const account = new BankAccount(100);
account.deposit(50);
console.log(account.getBalance()); // 150
```

## Problems It Solves
1. **Data Protection**: Prevents unauthorized access to sensitive data.
2. **Code Organization**: Bundles related data and methods together.

## Real-Life Usage
1. **Banking Systems**: Protecting sensitive financial data.
2. **Frameworks**: Encapsulating internal logic to prevent misuse.

## Pros
- **Security**: Protects sensitive data.
- **Modularity**: Improves code organization.

## Cons
- **Complexity**: Requires additional code for access control.
- **Performance**: Can add overhead if overused.

## Conclusion
Encapsulation is a fundamental concept in object-oriented programming. By understanding how it works, developers can write more secure and maintainable code.
