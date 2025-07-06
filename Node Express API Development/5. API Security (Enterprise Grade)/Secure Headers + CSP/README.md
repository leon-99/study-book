# Secure Headers + CSP

## Introduction
Secure headers and Content Security Policy (CSP) are mechanisms to enhance the security of web applications by preventing common attacks like cross-site scripting (XSS) and clickjacking. Secure headers are HTTP headers that instruct the browser on how to handle the application’s content.

## Real-Life Example
Think of a bank vault:
- The vault (secure headers) has specific rules for access and usage, ensuring that only authorized personnel can interact with it.

## Code Example
Using `helmet` to set secure headers:
```javascript
const express = require('express');
const helmet = require('helmet');
const app = express();

// Use helmet to set secure headers
app.use(helmet());

// Custom CSP configuration
app.use(
  helmet.contentSecurityPolicy({
    directives: {
      defaultSrc: ["'self'"],
      scriptSrc: ["'self'", 'trusted-scripts.com'],
      objectSrc: ["'none'"],
      upgradeInsecureRequests: []
    }
  })
);

app.get('/', (req, res) => res.send('Secure Headers Example'));

app.listen(3000, () => console.log('Server running on port 3000'));
```

## Problems It Solves
- **Prevents XSS**: Restricts the sources of scripts and content.
- **Mitigates Clickjacking**: Protects against UI redress attacks.
- **Enhances Security**: Enforces secure communication and content handling.

## Real-Life Usage
Secure headers and CSP are widely used in applications like online banking and e-commerce platforms to protect sensitive user data.

## Pros and Cons
### Pros
- Enhances application security.
- Prevents common web vulnerabilities.
- Easy to implement with libraries like `helmet`.

### Cons
- Requires careful configuration to avoid breaking functionality.
- Can be complex for dynamic content.

## Conclusion
Secure headers and CSP are essential for building secure web applications. By implementing these mechanisms, developers can protect their applications from common attacks and ensure a safe user experience.
