# WebSockets

## Introduction
WebSockets provide a full-duplex communication channel over a single TCP connection. This technology is ideal for real-time applications that require low-latency communication between the client and server.

## Real-Life Example
Think of a chat application:
- Messages are sent and received in real-time between users.

## Code Example
Using WebSocket with the `ws` library:
```javascript
const WebSocket = require('ws');

const wss = new WebSocket.Server({ port: 8080 });

wss.on('connection', (ws) => {
  console.log('Client connected');

  ws.on('message', (message) => {
    console.log(`Received: ${message}`);
    ws.send(`Echo: ${message}`);
  });

  ws.on('close', () => {
    console.log('Client disconnected');
  });
});

console.log('WebSocket server running on ws://localhost:8080');
```

## Problems It Solves
- **Real-Time Communication**: Enables instant data exchange.
- **Low Latency**: Reduces delays in communication.
- **Bidirectional Communication**: Allows both client and server to send messages.

## Real-Life Usage
WebSockets are used in applications like chat systems, online gaming, and live notifications.

## Pros and Cons
### Pros
- Low latency.
- Supports real-time communication.
- Efficient for frequent data exchange.

### Cons
- Requires WebSocket-compatible clients.
- May not be suitable for all use cases.

## Conclusion
WebSockets are a powerful tool for building real-time applications. By implementing WebSocket communication, developers can create interactive and responsive systems.
