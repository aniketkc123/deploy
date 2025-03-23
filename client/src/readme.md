# 🔗 URL Shortener API

A modern, fast, and scalable URL shortening service built with Node.js, React  and MongoDB.

## ⚡ Features

- Create short URLs from long URLs
- Custom short URL support
- Fast redirection

## 🛠️ Tech Stack

- **Runtime**: Node.js
- **Database**: MongoDB
- **Frontend** : React  
  
### Installation

1. Clone the repository
```bash
git clone https://github.com/aniketkc123/deploy

```

2. Install dependencies
```bash
cd server
npm i
cd cleint
npm i
```

3. Create a `.env` file in the root directory
```env
PORT=5000
MONGO_URI= your_mongodb_connection_string(enter your mongodb url string)
```

4. Start the development server
```bash
cd client
npm start
```

The API will be available at `http://localhost:5000`

## 📡 API Endpoints

### 1. Create Short URL
- **Endpoint**: `POST /api/urls`
- **Request Body**:
```json
{
    "longUrl": "https://example.com/very-long-url",
    "customUrl": "custom" (optional)
}
```
- **Response**:
```json
{
    "success": true,
    "data": {
        "longUrl": "https://example.com/very-long-url",
        "shortUrl": "abc123",
        "clicks": 0,
        "createdAt": "2024-03-22T..."
    }
}
```

### 2. Get URL Details
- **Endpoint**: `GET /api/urls/:shortUrl`
- **Response**:
```json
{
    "success": true,
    "data": {
        "longUrl": "https://example.com/very-long-url",
        "shortUrl": "abc123",
        "clicks": 5,
        "createdAt": "2024-03-22T..."
    }
}
```

### 3. Redirect to Long URL
- **Endpoint**: `GET /:shortUrl`
- **Action**: Redirects to the original long URL
- **Updates**: Increments the click counter

## 🏗️ Project Structure

```
url-shortener/
├── config/
│   └── db.js         # Database configuration
├── controllers/
│   └── url.js        # URL handling logic
├── models/
│   └── url.js        # URL database schema
├── routes/
│   └── url.routes.js # API routes
├── middleware/
│   └── error.js      # Error handling
├── server.js         # Main application file
└── vercel.json       # Vercel deployment config
```

## 🎯 Project Approach

1. **URL Shortening Algorithm**
   - Generate unique short codes using base62 encoding
   - Support custom URL paths
   - Ensure uniqueness in database

2. **Database Design**
   - Store URL mappings in MongoDB
   - Track analytics (clicks, creation date)
   - Index short URLs for fast lookups

3. **Performance Optimization**
   - Efficient database queries
   - Response caching
   - Load balancing ready



## 📈 Future Enhancements

- [ ] User authentication
- [ ] QR code generation
- [ ] Advanced analytics
- [ ] URL expiration
- [ ] API key management

## 🌐 Deployment

This API is deployed on Vercel. For deployment instructions:

1. Push code to GitHub
2. Connect repository to Vercel
3. Configure environment variables
4. Deploy!

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

---
Made with ❤️ by [Aniket Kumar Choudhary]
