# Message Queues

## Introduction
Message queues enable asynchronous communication between microservices by decoupling the sender and receiver. They ensure reliable message delivery and improve system scalability.

## Real-Life Example
Consider a food delivery app:
- The order service sends a message to the delivery service when an order is placed.
- The delivery service processes the message and assigns a delivery agent.

## Code Example
Using `RabbitMQ` for message queuing:

1. Install `amqplib`:
```bash
npm install amqplib
```

2. Producer:
```javascript
const amqp = require('amqplib');

async function sendMessage() {
  const connection = await amqp.connect('amqp://localhost');
  const channel = await connection.createChannel();
  const queue = 'orders';

  await channel.assertQueue(queue);
  channel.sendToQueue(queue, Buffer.from('New order placed'));

  console.log('Message sent');
  await channel.close();
  await connection.close();
}

sendMessage();
```

3. Consumer:
```javascript
const amqp = require('amqplib');

async function receiveMessage() {
  const connection = await amqp.connect('amqp://localhost');
  const channel = await connection.createChannel();
  const queue = 'orders';

  await channel.assertQueue(queue);
  channel.consume(queue, (message) => {
    console.log(`Received: ${message.content.toString()}`);
    channel.ack(message);
  });
}

receiveMessage();
```

## Problems It Solves
- **Asynchronous Communication**: Decouples services for better scalability.
- **Reliable Delivery**: Ensures messages are not lost.
- **Load Balancing**: Distributes messages across multiple consumers.

## Real-Life Usage
Message queues are used by:
- Uber for ride requests.
- LinkedIn for activity streams.
- Netflix for video encoding.

## Pros and Cons
### Pros
- Improves scalability and reliability.
- Supports asynchronous processing.
- Enables decoupling of services.

### Cons
- Adds complexity to the system.
- Requires monitoring and maintenance.
- May introduce latency in message delivery.

## Conclusion
Message queues are essential for building scalable and reliable microservices. They enable asynchronous communication and improve system performance, making them a key component of modern architectures.
