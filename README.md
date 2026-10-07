# Docker Practical Assignment

This project demonstrates basic Docker concepts and practical exercises.

## Topics Covered

- Docker installation and verification
- Docker images
- Docker containers
- Dockerfile
- Docker volumes
- Docker networks
- Docker Compose
- Docker Hub

## Application

A simple HTML application is containerized using Nginx.

## Docker Commands

Build image:

docker build -t vimala-docker-app:1.0 .

Run container:

docker run -d --name vimala-web -p 8081:80 vimala-docker-app:1.0

Run Docker Compose:

docker compose up -d --build

Stop Docker Compose:

docker compose down
Docker Compose

The Compose application contains:

Nginx web container
Redis container
Custom Docker network
Persistent Docker volume
