# In-memory Caching (Node-Cache)

## Introduction
In-memory caching stores frequently accessed data in the server's memory, reducing the need to fetch data from slower storage systems. `Node-Cache` is a lightweight caching module for Node.js that provides simple and efficient in-memory caching.

## Real-Life Example
Think of a coffee shop:
- The barista (server) keeps frequently ordered items (cached data) on the counter (memory) for quick access, instead of fetching them from the storage room (database) every time.

## Code Example
Using `Node-Cache` for in-memory caching:
```javascript
const NodeCache = require('node-cache');
const express = require('express');
const app = express();

const cache = new NodeCache({ stdTTL: 100, checkperiod: 120 });

// Middleware to check cache
const cacheMiddleware = (req, res, next) => {
  const key = req.url;
  const cachedData = cache.get(key);
  if (cachedData) {
    return res.send(cachedData);
  }
  res.sendResponse = res.send;
  res.send = (body) => {
    cache.set(key, body);
    res.sendResponse(body);
  };
  next();
};

app.use(cacheMiddleware);

app.get('/data', (req, res) => {
  res.send({ message: 'This is cached data' });
});

app.listen(3000, () => console.log('Server running on port 3000'));
```

## Problems It Solves
- **Reduces Latency**: Speeds up data retrieval.
- **Improves Performance**: Reduces load on the database.
- **Enhances Scalability**: Handles more requests efficiently.

## Real-Life Usage
In-memory caching is widely used in applications like e-commerce platforms to cache product details and reduce database queries.

## Pros and Cons
### Pros
- Fast and efficient.
- Easy to implement.
- Reduces database load.

### Cons
- Limited by server memory.
- Data is lost on server restart.

## Conclusion
In-memory caching with `Node-Cache` is a simple and effective way to improve the performance of Node.js applications. By caching frequently accessed data, developers can reduce latency and enhance scalability.
