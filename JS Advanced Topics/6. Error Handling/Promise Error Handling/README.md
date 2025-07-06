## Introduction
Handling errors in promises is crucial for building robust applications. JavaScript provides methods like `.catch` and `try...catch` (with `async/await`) to handle errors in promises effectively.

## Real-Life Example
Think of a delivery service. If a package is delayed (error), the service notifies you (error handling) and provides a resolution.

### Code Example
```javascript
// Using .catch
fetch('https://api.example.com/data')
    .then(response => {
        if (!response.ok) {
            throw new Error('Failed to fetch data');
        }
        return response.json();
    })
    .then(data => console.log(data))
    .catch(error => console.error('Error:', error));

// Using async/await
async function fetchData() {
    try {
        const response = await fetch('https://api.example.com/data');
        if (!response.ok) {
            throw new Error('Failed to fetch data');
        }
        const data = await response.json();
        console.log(data);
    } catch (error) {
        console.error('Error:', error);
    }
}

fetchData();
```

## Problems It Solves
1. **Error Handling**: Provides a structured way to handle errors in promises.
2. **Graceful Recovery**: Allows the application to recover from errors.

## Real-Life Usage
1. **API Calls**: Handling errors when fetching data from a server.
2. **File Operations**: Handling errors when reading or writing files.

## Pros
- **Error Handling**: Provides a structured way to handle errors.
- **Graceful Recovery**: Prevents application crashes.

## Cons
- **Complexity**: Requires careful handling to avoid masking errors.
- **Performance**: Can add overhead if overused.

## Conclusion
Handling errors in promises is essential for building robust applications. By understanding how to handle errors effectively, developers can write more reliable and maintainable code.
