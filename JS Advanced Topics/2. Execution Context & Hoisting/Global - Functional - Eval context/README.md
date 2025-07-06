# Global, Functional, and Eval Context

## Introduction
In JavaScript, the execution context defines the environment in which code is executed. There are three main types of execution contexts: global, functional, and eval. Understanding these contexts is crucial for mastering JavaScript's behavior.

## Real-Life Example
Imagine a theater with three types of spaces: the main stage (global context), individual dressing rooms (functional context), and temporary rehearsal spaces (eval context). Each space has its own rules and resources.

### Code Example
```javascript
// Global Context
let globalVar = 'I am global';

function showContext() {
    // Functional Context
    let localVar = 'I am local';
    console.log(globalVar); // Accessible
    console.log(localVar); // Accessible
}

showContext();

// Eval Context
eval('let evalVar = "I am eval"; console.log(evalVar);');
```

## Problems It Solves
1. **Code Organization**: Execution contexts help in structuring code logically.
2. **Variable Scope**: They define the accessibility of variables and functions.

## Real-Life Usage
1. **Global Context**: Used for defining application-wide constants and configurations.
   ```javascript
   const APP_NAME = 'MyApp';
   console.log(`Welcome to ${APP_NAME}`);
   ```

2. **Functional Context**: Used for encapsulating logic and creating reusable functions.
   ```javascript
   function greetUser(name) {
       console.log(`Hello, ${name}!`);
   }

   greetUser('Alice');
   ```

3. **Eval Context**: Rarely used but can dynamically execute code strings.
   ```javascript
   eval('console.log("This is eval context");');
   ```

## Pros
- **Flexibility**: Allows for dynamic and organized code execution.
- **Encapsulation**: Functional context provides a way to encapsulate logic.

## Cons
- **Global Pollution**: Overuse of global context can lead to conflicts.
- **Security Risks**: Eval context can introduce vulnerabilities.

## Conclusion
Understanding execution contexts is fundamental for writing efficient and secure JavaScript code. Each context serves a specific purpose and should be used appropriately.