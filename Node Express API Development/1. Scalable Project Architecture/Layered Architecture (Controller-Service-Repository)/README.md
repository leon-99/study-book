# Layered Architecture (Controller-Service-Repository)

## Introduction
Layered architecture is a design pattern that separates an application into distinct layers, each with a specific responsibility. In Node.js and Express, this typically includes the Controller, Service, and Repository layers. This separation of concerns makes the codebase more maintainable and scalable.

## Real-Life Example
Imagine a restaurant:
- The **Controller** is like the waiter who takes your order.
- The **Service** is the kitchen staff who prepare the food.
- The **Repository** is the storage room where ingredients are kept.
Each has a distinct role, ensuring smooth operations.

## Code Example
```javascript
// Controller
const userService = require('./userService');

exports.getUser = async (req, res) => {
  try {
    const user = await userService.getUserById(req.params.id);
    res.status(200).json(user);
  } catch (error) {
    res.status(500).json({ error: error.message });
  }
};

// Service
const userRepository = require('./userRepository');

exports.getUserById = async (id) => {
  return await userRepository.findById(id);
};

// Repository
const db = require('./db');

exports.findById = async (id) => {
  return db.users.find(user => user.id === id);
};
```

## Problems It Solves
- **Maintainability**: Changes in one layer do not affect others.
- **Scalability**: Easier to add new features.
- **Testability**: Each layer can be tested independently.

## Real-Life Usage
This pattern is widely used in enterprise applications, such as e-commerce platforms, where clear separation of concerns is crucial for managing complex business logic.

## Pros and Cons
### Pros
- Clear separation of concerns.
- Easier debugging and testing.
- Promotes reusability.

### Cons
- Can introduce complexity.
- Overhead in smaller applications.

## Conclusion
Layered architecture is a powerful design pattern for building scalable and maintainable applications. By separating concerns into distinct layers, developers can focus on specific aspects of the application without being overwhelmed by its entirety.
