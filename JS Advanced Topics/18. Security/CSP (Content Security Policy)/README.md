# CSP (Content Security Policy)

## Introduction
Content Security Policy (CSP) is a security feature that helps prevent attacks like Cross-Site Scripting (XSS) by restricting the sources from which content can be loaded.

## Real-Life Example
Consider a web application that only allows scripts from its own domain. CSP ensures that malicious scripts from other domains cannot be executed.

## Code Example
```html
<meta http-equiv="Content-Security-Policy" content="default-src 'self'; script-src 'self' https://apis.example.com">
```

## Problems It Solves
- Prevents XSS attacks
- Restricts unauthorized content loading

## Real-Life Usage
1. **Web applications**: Enforcing strict content policies.
2. **Third-party scripts**: Allowing only trusted sources.

## Pros
- Enhances security
- Reduces attack surface

## Cons
- Requires careful configuration
- May break functionality if misconfigured

## Conclusion
CSP is a powerful tool for securing web applications, providing a robust defense against XSS and other content-based attacks.
