# fetch and XMLHttpRequest

## Introduction
`fetch` and `XMLHttpRequest` are APIs in JavaScript used to make HTTP requests. While `XMLHttpRequest` is older and more complex, `fetch` provides a modern and simpler alternative.

## Real-Life Example
Consider a weather application that fetches data from an API to display the current weather conditions.

## Code Example
```javascript
// Using fetch
fetch('https://api.example.com/weather')
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));

// Using XMLHttpRequest
const xhr = new XMLHttpRequest();
xhr.open('GET', 'https://api.example.com/weather');
xhr.onload = () => console.log(JSON.parse(xhr.responseText));
xhr.onerror = () => console.error('Error');
xhr.send();
```

## Problems It Solves
- Enables communication with servers
- Fetches data dynamically without reloading the page

## Real-Life Usage
1. **API integration**: Fetching data from external APIs.
2. **Dynamic content**: Loading content dynamically based on user actions.

## Pros
- `fetch` is simpler and more modern
- Both support asynchronous operations

## Cons
- `XMLHttpRequest` is verbose and outdated
- `fetch` lacks built-in progress tracking

## Conclusion
`fetch` and `XMLHttpRequest` are essential tools for making HTTP requests in JavaScript, with `fetch` being the preferred choice for modern applications.
