# Event App

# REST API built with Go and Gin framework for event management with user authentication.  

## Development Setup 。

This project uses Air for live reload during development. Here's how to get started:

1. Install Air:

```bash
go install github.com/cosmtrek/air@latest
```

2. Run the application with Air:

```bash
air
```

### Running the Application

After building, you can run the application using:

```bash
./api
```

The server will start on `http://localhost:8080` by default.

### API Usage  

Examples:  

### Register User  

```bash
curl -X POST http://localhost:8080/api/v1/auth/register \
  -H "Content-Type: application/json" \
  -d '{
    "email": "test@example.com",
    "password": "password123", 
    "name": "Test User"
  }'
```

### Login & Get Token  

```bash
curl -X POST http://localhost:8080/api/v1/auth/login \
  -H "Content-Type: application/json" \
  -d '{
    "email": "test@example.com",
    "password": "password123"
  }'
```

### Create Event (requires token)  

```bash
curl -X POST http://localhost:8080/api/v1/events \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer <your-token>" \
  -d '{
    "name": "Go Conference",
    "description": "A conference about Go",
    "date": "2025-05-20",
    "location": "San Francisco"
  }'
```