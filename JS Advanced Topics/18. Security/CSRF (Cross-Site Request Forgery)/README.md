# CSRF (Cross-Site Request Forgery)

## Introduction
Cross-Site Request Forgery (CSRF) is an attack that tricks a user into performing actions they did not intend to perform. CSRF tokens are used to prevent such attacks.

## Real-Life Example
Consider a banking application where a malicious website tricks a logged-in user into transferring money without their consent. CSRF protection prevents this.

## Code Example
```html
<form method="POST" action="/transfer">
  <input type="hidden" name="csrf_token" value="123456">
  <button type="submit">Transfer</button>
</form>
```

## Problems It Solves
- Prevents unauthorized actions
- Protects sensitive operations

## Real-Life Usage
1. **Banking apps**: Securing transactions.
2. **Web forms**: Protecting form submissions.

## Pros
- Enhances security
- Easy to implement with frameworks

## Cons
- Requires server-side support
- Adds complexity to forms

## Conclusion
CSRF protection is essential for securing web applications, ensuring that users perform only the actions they intend.
