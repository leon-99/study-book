# CommonJS (require)

## Introduction
CommonJS is a module system used in Node.js to manage dependencies and organize code into reusable modules. It uses the `require` function to import modules and `module.exports` to export them.

## Real-Life Example
Imagine a library system where different sections (e.g., books, members, loans) are managed separately. CommonJS allows you to create modules for each section and import them as needed.

## Code Example
```javascript
// books.js
module.exports = {
  getBooks: () => ["Book1", "Book2"],
};

// app.js
const books = require("./books");
console.log(books.getBooks());
```

## Problems It Solves
- Code organization
- Dependency management
- Reusability of code

## Real-Life Usage
CommonJS is widely used in Node.js applications for server-side development.

## Pros
- Simple syntax
- Synchronous loading (suitable for server-side)

## Cons
- Not suitable for browsers without bundlers
- Synchronous nature can be a limitation in some cases

## Conclusion
CommonJS is a robust module system for server-side JavaScript, but modern applications often use ES Modules for better browser compatibility.
