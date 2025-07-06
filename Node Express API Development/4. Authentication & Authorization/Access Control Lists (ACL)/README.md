# Access Control Lists (ACL)

## Introduction
Access Control Lists (ACL) are a method of defining permissions for users or roles to access specific resources in an application. ACLs provide fine-grained control over who can perform what actions on which resources.

## Real-Life Example
Think of a library:
- A librarian (admin) can add or remove books.
- A member (user) can borrow books but cannot modify the catalog.
- A guest (visitor) can only view the catalog.

## Code Example
Using a simple ACL implementation:
```javascript
const express = require('express');
const app = express();

// Mock user roles
const users = {
  admin: { role: 'admin' },
  user: { role: 'user' },
  guest: { role: 'guest' }
};

// ACL middleware
const acl = (allowedRoles) => (req, res, next) => {
  const user = users[req.query.user]; // Mock user from query
  if (!user || !allowedRoles.includes(user.role)) {
    return res.status(403).send('Access Denied');
  }
  next();
};

// Routes
app.get('/admin', acl(['admin']), (req, res) => res.send('Welcome Admin'));
app.get('/user', acl(['admin', 'user']), (req, res) => res.send('Welcome User'));
app.get('/guest', acl(['admin', 'user', 'guest']), (req, res) => res.send('Welcome Guest'));

app.listen(3000, () => console.log('Server running on port 3000'));
```

## Problems It Solves
- **Fine-Grained Control**: Defines specific permissions for users or roles.
- **Improves Security**: Restricts access to sensitive resources.
- **Enhances Flexibility**: Supports dynamic permission management.

## Real-Life Usage
ACLs are widely used in applications like content management systems (CMS), where different roles (e.g., editor, author, viewer) have varying levels of access to resources.

## Pros and Cons
### Pros
- Provides fine-grained access control.
- Enhances application security.
- Supports dynamic role-based permissions.

### Cons
- Can become complex in large applications.
- Requires careful management to avoid conflicts.

## Conclusion
Access Control Lists (ACL) are a powerful tool for managing permissions in applications. By defining roles and their associated permissions, developers can ensure secure and flexible access control for their systems.
