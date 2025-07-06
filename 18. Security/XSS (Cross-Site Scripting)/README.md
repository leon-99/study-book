# XSS (Cross-Site Scripting)

## Introduction
Cross-Site Scripting (XSS) is a security vulnerability that allows attackers to inject malicious scripts into web pages viewed by other users. Preventing XSS involves sanitizing inputs and using secure coding practices.

## Real-Life Example
Consider a comment section where users can post comments. If inputs are not sanitized, an attacker could inject a script that steals user cookies.

## Code Example
```javascript
const userInput = '<script>alert("XSS")</script>';
const sanitizedInput = userInput.replace(/</g, '&lt;').replace(/>/g, '&gt;');
console.log(sanitizedInput); // &lt;script&gt;alert("XSS")&lt;/script&gt;
```

## Problems It Solves
- Prevents malicious script execution
- Protects user data and application integrity

## Real-Life Usage
1. **Comment sections**: Preventing script injection.
2. **Search bars**: Ensuring safe user queries.

## Pros
- Enhances security
- Protects users and applications

## Cons
- Requires careful implementation
- May impact functionality if overly strict

## Conclusion
Preventing XSS is essential for securing web applications, ensuring that user inputs are safe and do not compromise the application or its users.
