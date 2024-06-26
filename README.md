# URL Shortener 

This project implements a URL shortener service written in Go that leverages Redis for efficient storage and retrieval of shortened URLs. It utilizes Docker and Docker Compose for streamlined development, deployment, and scaling.

## Features

- URL Shortening: Create concise, custom (optional) shortened URLs for long original URLs.
- Redirection: Seamlessly redirects users from shortened URLs to their corresponding original URLs.
- Redis Integration: Optimizes performance and scalability using Redis as the data store.
- Go Fiber: Utilizes the high-performance Go Fiber web framework for efficient request handling.
- Rate Limiting: Enforces limits on API requests to prevent abuse and improve server stability.
- Dockerized: Enhances portability and simplifies deployment with Docker containers.
- Docker Compose: Streamlines running multiple services (application and Redis) together.
