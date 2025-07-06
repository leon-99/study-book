# Avoiding Injection Attacks (XSS, SQLi)

## Introduction
Injection attacks, such as Cross-Site Scripting (XSS) and SQL Injection (SQLi), are among the most common and dangerous vulnerabilities in web applications. These attacks exploit improper input handling to execute malicious code or queries.

## Real-Life Example
Think of a vending machine:
- If the machine accepts any input (e.g., coins, buttons) without validation, someone could insert fake coins or tamper with its mechanism to get free snacks.

## Code Example
### Preventing XSS
Using `express-validator` to sanitize input:
```javascript
const express = require('express');
const { body, validationResult } = require('express-validator');
const app = express();

app.use(express.json());

app.post('/submit',
  body('name').trim().escape(), // Sanitize input
  (req, res) => {
    const errors = validationResult(req);
    if (!errors.isEmpty()) {
      return res.status(400).json({ errors: errors.array() });
    }
    res.send(`Hello, ${req.body.name}`);
  }
);

app.listen(3000, () => console.log('Server running on port 3000'));
```

### Preventing SQLi
Using parameterized queries with `mysql2`:
```javascript
const mysql = require('mysql2');
const connection = mysql.createConnection({
  host: 'localhost',
  user: 'root',
  database: 'test'
});

const userId = 1; // Example user input
connection.execute('SELECT * FROM users WHERE id = ?', [userId], (err, results) => {
  if (err) throw err;
  console.log(results);
});
```

## Problems It Solves
- **Prevents XSS**: Sanitizes user input to remove malicious scripts.
- **Prevents SQLi**: Uses parameterized queries to avoid query manipulation.
- **Enhances Security**: Protects sensitive data and application integrity.

## Real-Life Usage
Injection prevention techniques are essential in applications like online banking and e-commerce platforms, where user input is processed and stored securely.

## Pros and Cons
### Pros
- Protects against common and severe vulnerabilities.
- Enhances application security and user trust.
- Easy to implement with modern libraries and frameworks.

### Cons
- Requires consistent input validation and sanitization.
- Can add complexity to input handling.

## Conclusion
Avoiding injection attacks is critical for building secure web applications. By implementing input validation, sanitization, and parameterized queries, developers can protect their applications from XSS, SQLi, and other injection vulnerabilities.
