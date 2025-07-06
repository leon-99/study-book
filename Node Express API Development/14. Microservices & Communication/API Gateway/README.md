# API Gateway

## Introduction
An API Gateway acts as a single entry point for client requests in a microservices architecture. It handles tasks like request routing, authentication, rate limiting, and load balancing.

## Real-Life Example
Consider a travel booking platform:
- The API Gateway routes requests to services like flights, hotels, and car rentals.
- It also handles authentication and rate limiting for client requests.

## Code Example
Using `Express Gateway` to set up an API Gateway:

1. Install `express-gateway`:
```bash
npm install -g express-gateway
```

2. Create a new gateway:
```bash
eg gateway create my-gateway
```

3. Configure the gateway:
Edit `gateway.config.yml`:
```yaml
http:
  port: 8080
apiEndpoints:
  default:
    host: localhost
serviceEndpoints:
  flights:
    url: 'http://localhost:3001'
  hotels:
    url: 'http://localhost:3002'
policies:
  - proxy
pipelines:
  default:
    apiEndpoints:
      - default
    policies:
      - proxy:
          - action:
              serviceEndpoint: flights
```

4. Start the gateway:
```bash
npm start
```

## Problems It Solves
- **Centralized Management**: Simplifies client interactions with multiple services.
- **Security**: Handles authentication and rate limiting.
- **Scalability**: Distributes traffic across services.

## Real-Life Usage
API Gateways are used by:
- Netflix for its microservices.
- Amazon for its e-commerce platform.
- Spotify for its music streaming services.

## Pros and Cons
### Pros
- Simplifies client interactions.
- Enhances security and scalability.
- Provides centralized monitoring and logging.

### Cons
- Adds a single point of failure.
- Increases system complexity.
- May introduce latency.

## Conclusion
An API Gateway is a vital component of microservices architecture. It simplifies client interactions, enhances security, and improves scalability, making it essential for modern distributed systems.
