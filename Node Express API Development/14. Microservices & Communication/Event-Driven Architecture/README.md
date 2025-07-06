# Event-Driven Architecture

## Introduction
Event-driven architecture (EDA) is a design pattern where services communicate by producing and consuming events. It enables real-time data processing and decouples services for better scalability.

## Real-Life Example
Consider a social media platform:
- When a user posts a photo, an event is generated.
- Services like notifications, analytics, and feeds consume the event to update their respective data.

## Code Example
Using `Kafka` for event-driven architecture:

1. Install `kafkajs`:
```bash
npm install kafkajs
```

2. Producer:
```javascript
const { Kafka } = require('kafkajs');

const kafka = new Kafka({ brokers: ['localhost:9092'] });
const producer = kafka.producer();

async function produceEvent() {
  await producer.connect();
  await producer.send({
    topic: 'user-events',
    messages: [{ value: 'User signed up' }],
  });

  console.log('Event produced');
  await producer.disconnect();
}

produceEvent();
```

3. Consumer:
```javascript
const { Kafka } = require('kafkajs');

const kafka = new Kafka({ brokers: ['localhost:9092'] });
const consumer = kafka.consumer({ groupId: 'analytics' });

async function consumeEvent() {
  await consumer.connect();
  await consumer.subscribe({ topic: 'user-events', fromBeginning: true });

  await consumer.run({
    eachMessage: async ({ message }) => {
      console.log(`Received: ${message.value.toString()}`);
    },
  });
}

consumeEvent();
```

## Problems It Solves
- **Real-Time Processing**: Enables immediate reaction to events.
- **Decoupling**: Reduces dependencies between services.
- **Scalability**: Supports high-throughput data streams.

## Real-Life Usage
Event-driven architecture is used by:
- Amazon for order processing.
- Uber for ride matching.
- Spotify for real-time recommendations.

## Pros and Cons
### Pros
- Enables real-time data processing.
- Improves scalability and flexibility.
- Decouples services for better maintainability.

### Cons
- Adds complexity to the system.
- Requires robust event management.
- May lead to eventual consistency issues.

## Conclusion
Event-driven architecture is a powerful pattern for building scalable and responsive systems. By leveraging events, developers can create decoupled and real-time applications.
