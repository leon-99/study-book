# Sanitizing Inputs

## Introduction
Sanitizing inputs in JavaScript involves cleaning and validating user-provided data to prevent security vulnerabilities like SQL injection and XSS.

## Real-Life Example
Consider a search bar where users can input queries. Sanitizing the input ensures that malicious scripts cannot be executed.

## Code Example
```javascript
function sanitizeInput(input) {
  const div = document.createElement('div');
  div.textContent = input;
  return div.innerHTML;
}

const userInput = '<script>alert("XSS")</script>';
console.log(sanitizeInput(userInput)); // &lt;script&gt;alert("XSS")&lt;/script&gt;
```

## Problems It Solves
- Prevents XSS and SQL injection
- Ensures data integrity

## Real-Life Usage
1. **Search bars**: Cleaning user queries.
2. **Form inputs**: Validating and sanitizing user data.

## Pros
- Enhances security
- Improves data quality

## Cons
- Requires careful implementation
- May impact user experience if overly strict

## Conclusion
Sanitizing inputs is a critical practice for securing web applications, ensuring that user-provided data is safe and valid.
