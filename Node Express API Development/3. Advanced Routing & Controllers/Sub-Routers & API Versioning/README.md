# Sub-Routers & API Versioning

## Introduction
Sub-routers and API versioning are techniques used to organize and manage routes in large applications. Sub-routers allow grouping of related routes, while API versioning ensures backward compatibility as the application evolves.

## Real-Life Example
Think of a library:
- Different sections (sub-routers) like fiction, non-fiction, and reference are organized for easy navigation.
- New editions (API versions) of books are added without removing old ones.

## Code Example
```javascript
const express = require('express');
const app = express();

// Sub-router for v1
const v1Router = express.Router();
v1Router.get('/users', (req, res) => res.send('User List v1'));
v1Router.get('/products', (req, res) => res.send('Product List v1'));

// Sub-router for v2
const v2Router = express.Router();
v2Router.get('/users', (req, res) => res.send('User List v2'));
v2Router.get('/products', (req, res) => res.send('Product List v2'));

// Use sub-routers
app.use('/api/v1', v1Router);
app.use('/api/v2', v2Router);

app.listen(3000, () => console.log('Server running on port 3000'));
```

## Problems It Solves
- **Organization**: Groups related routes for better structure.
- **Backward Compatibility**: Supports multiple API versions.
- **Scalability**: Simplifies adding new features or versions.

## Real-Life Usage
Sub-routers and API versioning are commonly used in RESTful APIs, such as social media platforms, where different versions of user and post APIs are maintained.

## Pros and Cons
### Pros
- Promotes modularity and scalability.
- Ensures backward compatibility.
- Simplifies route management.

### Cons
- Requires additional setup.
- Can lead to versioning conflicts if not managed properly.

## Conclusion
Sub-routers and API versioning are essential for building scalable and maintainable Express.js applications. By organizing routes and supporting multiple versions, developers can ensure a smooth evolution of the application.
