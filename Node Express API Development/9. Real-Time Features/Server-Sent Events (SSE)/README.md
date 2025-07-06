# Server-Sent Events (SSE)

## Introduction
Server-Sent Events (SSE) allow servers to push updates to the client over a single HTTP connection. This technology is ideal for real-time applications that require one-way communication from the server to the client.

## Real-Life Example
Think of a stock ticker:
- The server sends real-time stock price updates to the client.

## Code Example
Using SSE with Express:
```javascript
const express = require('express');
const app = express();

app.get('/events', (req, res) => {
  res.setHeader('Content-Type', 'text/event-stream');
  res.setHeader('Cache-Control', 'no-cache');
  res.setHeader('Connection', 'keep-alive');

  const sendEvent = (data) => {
    res.write(`data: ${JSON.stringify(data)}\n\n`);
  };

  const interval = setInterval(() => {
    sendEvent({ message: 'Hello, client!' });
  }, 1000);

  req.on('close', () => {
    clearInterval(interval);
    res.end();
  });
});

app.listen(3000, () => console.log('Server running on port 3000'));
```

## Problems It Solves
- **Real-Time Updates**: Pushes data to the client as it becomes available.
- **Low Overhead**: Uses a single HTTP connection.
- **Simple Implementation**: Easy to set up with HTTP.

## Real-Life Usage
SSE is used in applications like live score updates, stock tickers, and real-time dashboards.

## Pros and Cons
### Pros
- Simple to implement.
- Works with standard HTTP.
- Low overhead for one-way communication.

### Cons
- Limited to one-way communication.
- Not supported in all browsers.

## Conclusion
Server-Sent Events are a great choice for real-time applications that require one-way communication. By using SSE, developers can build efficient and responsive systems.
