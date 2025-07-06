# File Uploads

## Introduction
File uploads are a common feature in web applications, allowing users to upload files such as images, documents, and videos to the server. In Node.js, libraries like `multer` make handling file uploads straightforward.

## Real-Life Example
Think of a photo-sharing app:
- Users upload images to share with others.

## Code Example
Using `multer` for file uploads:
```javascript
const express = require('express');
const multer = require('multer');
const app = express();

// Configure multer storage
const storage = multer.diskStorage({
  destination: (req, file, cb) => {
    cb(null, 'uploads/');
  },
  filename: (req, file, cb) => {
    cb(null, `${Date.now()}-${file.originalname}`);
  },
});

const upload = multer({ storage });

// Route for file upload
app.post('/upload', upload.single('file'), (req, res) => {
  res.send(`File uploaded: ${req.file.filename}`);
});

app.listen(3000, () => console.log('Server running on port 3000'));
```

## Problems It Solves
- **User Interaction**: Allows users to upload files.
- **Data Storage**: Stores files for later use.
- **Scalability**: Supports large file uploads with proper configuration.

## Real-Life Usage
File uploads are used in applications like social media platforms, e-commerce websites, and content management systems.

## Pros and Cons
### Pros
- Easy to implement with libraries like `multer`.
- Supports various storage options (disk, memory, cloud).
- Handles file validation and size limits.

### Cons
- Requires proper security measures to prevent malicious uploads.
- Can consume significant server resources for large files.

## Conclusion
File uploads are an essential feature for many web applications. By using libraries like `multer`, developers can implement this functionality efficiently and securely.
