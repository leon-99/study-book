# File Streaming

## Introduction
File streaming allows applications to process and deliver files in chunks, rather than loading the entire file into memory. This approach is ideal for handling large files efficiently.

## Real-Life Example
Think of a video streaming service:
- Videos are streamed in chunks to reduce buffering and improve performance.

## Code Example
Using Node.js streams for file streaming:
```javascript
const express = require('express');
const fs = require('fs');
const path = require('path');
const app = express();

// Route for file streaming
app.get('/stream', (req, res) => {
  const filePath = path.join(__dirname, 'files', 'large-video.mp4');
  const stat = fs.statSync(filePath);
  const fileSize = stat.size;
  const range = req.headers.range;

  if (range) {
    const parts = range.replace(/bytes=/, '').split('-');
    const start = parseInt(parts[0], 10);
    const end = parts[1] ? parseInt(parts[1], 10) : fileSize - 1;

    const chunkSize = end - start + 1;
    const file = fs.createReadStream(filePath, { start, end });
    const head = {
      'Content-Range': `bytes ${start}-${end}/${fileSize}`,
      'Accept-Ranges': 'bytes',
      'Content-Length': chunkSize,
      'Content-Type': 'video/mp4',
    };

    res.writeHead(206, head);
    file.pipe(res);
  } else {
    const head = {
      'Content-Length': fileSize,
      'Content-Type': 'video/mp4',
    };
    res.writeHead(200, head);
    fs.createReadStream(filePath).pipe(res);
  }
});

app.listen(3000, () => console.log('Server running on port 3000'));
```

## Problems It Solves
- **Efficient File Handling**: Processes large files without consuming excessive memory.
- **Improved Performance**: Delivers files in chunks for faster access.
- **Scalability**: Supports concurrent file streaming.

## Real-Life Usage
File streaming is used in applications like video streaming platforms, audio streaming services, and large file downloads.

## Pros and Cons
### Pros
- Efficient memory usage.
- Supports large files.
- Enhances user experience with faster access.

### Cons
- Requires additional implementation effort.
- May need optimization for high-concurrency scenarios.

## Conclusion
File streaming is a powerful technique for handling large files efficiently. By implementing streaming, developers can build scalable and high-performance applications.
