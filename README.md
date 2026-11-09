# Go HTTP Server

A simple HTTP web server built using **Go's standard `net/http` package**. This project is part of my journey learning backend development with Golang.

The goal is to understand how HTTP servers work, how requests are handled, how routing works, and how clients communicate with a backend server — without using any external web frameworks.

## Features

- Built-in HTTP server using Go's `net/http`.
- Serves static files using `http.FileServer`.
- Handles GET requests.
- Handles POST requests.
- Basic request validation using HTTP methods.
- Parses submitted form data.
- Extracts values from HTTP requests.
- Handles HTTP errors and responses.
- Routes requests using Go's built-in `ServeMux`.

## Tech Stack

- **Language:** Go (Golang)
- **HTTP Library:** `net/http`
- **Other Packages:** `fmt`, `log`

## Project Structure

```text
.
├── main.go
├── index.html
├── form.html
├── go.mod
└── README.md
```

## Getting Started

### 1. Clone the repository

```bash
git clone <your-repository-url>
cd <repository-name>
```

### 2. Initialize the Go module

If the project doesn't already have a `go.mod` file:

```bash
go mod init myproject
```

### 3. Run the server

```bash
go run .
```

The server will start at:

```text
http://localhost:8080
```

## Available Routes

| Method | Endpoint | Description |
|---|---|---|
| GET | `/` | Serves the home page |
| GET | `/hello` | Returns a hello message |
| GET | `/form.html` | Serves the contact form |
| POST | `/form` | Processes submitted form data |

## Testing the API

### Hello endpoint

```bash
curl http://localhost:8080/hello
```

Expected response:

```text
hello!
```

### Form endpoint

```bash
curl -X POST http://localhost:8080/form \
  -d "name=Divyansh" \
  -d "address=Bhopal"
```

Expected response:

```text
POST request successful
Name = Divyansh
Address = Bhopal
```
