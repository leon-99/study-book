## Introduction
Lexical scope, also known as static scope, is a fundamental concept in JavaScript. It determines how variable names are resolved in nested functions based on their position in the source code.

## Real-Life Example
Imagine a building with multiple floors. Each floor has its own set of keys. If you are on a specific floor, you can access the keys on that floor and the floors below it, but not the floors above. Similarly, in JavaScript, functions can access variables in their own scope and in the scope of their parent functions.

### Code Example
```javascript
function outerFunction() {
    let outerVariable = 'I am from the outer scope';

    function innerFunction() {
        console.log(outerVariable); // Accessible because of lexical scope
    }

    innerFunction();
}

outerFunction();
```

## Problems It Solves
1. **Predictability**: Lexical scoping makes it easier to predict how variables will behave in nested functions.
2. **Encapsulation**: It allows functions to encapsulate their variables, preventing unintended interference from other parts of the code.

## Real-Life Usage
1. **Function Factories**: Lexical scope allows function factories to create specialized functions with access to shared variables.
   ```javascript
   function createMultiplier(multiplier) {
       return function(value) {
           return value * multiplier;
       };
   }

   const double = createMultiplier(2);
   const triple = createMultiplier(3);

   console.log(double(5)); // 10
   console.log(triple(5)); // 15
   ```

2. **Configuration Objects**: Lexical scope is used to retain configuration settings in libraries and frameworks.
   ```javascript
   function configureLibrary(settings) {
       return function() {
           console.log(`Using settings: ${JSON.stringify(settings)}`);
       };
   }

   const logger = configureLibrary({ level: 'debug' });
   logger(); // Using settings: {"level":"debug"}
   ```

## Pros
- **Readability**: Makes the code easier to understand and debug.
- **Security**: Variables are not accessible outside their intended scope.

## Cons
- **Complexity in Deep Nesting**: Deeply nested functions can make the code harder to read.
- **Memory Usage**: Variables in the outer scope remain in memory as long as they are referenced by inner functions.

## Conclusion
Understanding lexical scope is crucial for writing efficient and bug-free JavaScript code. It forms the foundation for more advanced concepts like closures and modules.