# URL Shortener 

This project implements a URL shortener service written in Go that leverages Redis for efficient storage and retrieval of shortened URLs. It utilizes Docker and Docker Compose for streamlined development, deployment, and scaling.

## Features

- **URL Shortening**: Create concise, custom (optional) shortened URLs for long original URLs.
- **Redirection**: Seamlessly redirects users from shortened URLs to their corresponding original URLs.
- **Redis Integration**: Optimizes performance and scalability using Redis as the data store.
- **Go Fiber**: Utilizes the high-performance Go Fiber web framework for efficient request handling.
- **Rate Limiting**: Enforces limits on API requests to prevent abuse and improve server stability.
- **Dockerized**: Enhances portability and simplifies deployment with Docker containers.
- **Docker Compose**: Streamlines running multiple services (application and Redis) together.

## Prerequisites
- Go version 1.17 or later (https://go.dev/doc/install)
- Docker (https://www.docker.com/)
- Docker Compose (https://docs.docker.com/compose/install/)

## Setup
1. Clone the Repository:
 ```bash
git clone https://github.com/jyotiprakashh/url-shortner.git
cd url-shortner
```
2. Start the Services:
 ```bash
docker-compose up -d
```

This command will build the necessary Docker images (application and Redis) and run them in detached mode.

## Usage:
The application currently focuses on a command-line interface. You can interact with it using environment variables defined in the .env file (create one if it doesn't exist). 

## Environment Variables:
```bash
DB_ADDR="db:6379"
DB_PASS=""
APP_PORT= ":3000"
DOMAIN="localhost:3000"
API_QUOTA=10
```

## Example Usage:
- Shorten a URL (replace http://longurl.example.com with your desired URL):
```bash
curl -X POST http://localhost:3000/api/v1 -d '{"url":"http://longurl.example.com"}'
```

- Shorten the URL with custom names also:
```bash
curl -X POST http://localhost:3000/api/v1 -d '{"url":"http://longurl.example.com", "short":"custom_name"}'
```

- Redirect to the original URL:
```bash
curl http://localhost:8080/custom_name
```


## Configuration:
- You can customize environment variables in the .env file to adjust the application's behavior (e.g., modify rate limiting values).
- Additional configuration options might be added in the future, which will be documented here.
