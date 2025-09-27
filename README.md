# Simple Authentication Examples

This project demonstrates different methods of implementing authentication in Node.js applications using Express. It includes examples of basic authentication and cookie-based authentication.

## Project Structure

```
simple_auth/
├── basic_auth.js    # Basic HTTP Authentication example
├── cookie_auth.js   # Cookie-based Authentication example
└── package.json     # Project dependencies
```

## Features

### Basic Authentication (basic_auth.js)
- Simple HTTP Basic Authentication implementation
- Protected and public routes
- Hardcoded credentials (for demo purposes)
- Uses Express middleware for authentication

### Cookie Authentication (cookie_auth.js)
- MongoDB-based session management
- Cookie-based authentication
- Auto-expiring sessions (5 minutes)
- Secure cookie handling with httpOnly flag
- Login, logout, and protected route implementation

## Dependencies

- Express.js (^5.1.0)
- Cookie-parser (^1.4.7)
- Mongoose (^8.18.2)
- UUID (^13.0.0)

## Getting Started

1. Install dependencies:
```bash
npm install
```

2. Make sure MongoDB is running (required for cookie_auth.js):
```bash
mongod
```

3. Run the basic authentication server:
```bash
node basic_auth.js
```
The server will start on http://localhost:3000

4. Run the cookie authentication server:
```bash
node cookie_auth.js
```
The server will start on http://localhost:3001

## API Endpoints

### Basic Authentication (Port 3000)

- `GET /` - Public route
- `GET /public` - Public route
- `GET /secure` - Protected route (requires authentication)
  - Username: admin
  - Password: 12345
- node basic_auth.js.  
- Hint to add authorization field in request header
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/59b3bf99-7c93-4f30-a2cd-5c3e6069d819" />
### Cookie Authentication (Port 3001)

- `POST /login` - Login endpoint (requires username and password in request body)
- `GET /profile` - Protected route (requires valid cookie)
- `POST /logout` - Logout endpoint (clears authentication cookie)

Example login request:
```json
{
  "username": "admin",
  "password": "12345"
}
```
-node cookie_auth.js
- Hint to show cookie
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/21269f5f-f8aa-4dd4-b668-80908a58fcfa" />
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/46d975e5-3e5e-484c-93c8-f47752eaa467" />
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/40ddf9eb-eba9-4859-98a4-7df7d2afdea7" />



## Security Notes

This is a demonstration project and includes several practices that should be modified for production use:

- Passwords should be hashed, not stored in plain text
- Credentials should not be hardcoded
- Additional security headers should be implemented
- Error handling should be more robust
- Environment variables should be used for sensitive data

## License

ISC






