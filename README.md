# Docker Practical Assignment

This project demonstrates basic Docker concepts and practical exercises, including Docker images, containers, Dockerfiles, volumes, networks, Docker Compose, and Docker Hub.

## Project Structure

docker-practical-assignment/

│

├── index.html

├── Dockerfile

├── docker-compose.yml

├── README.md

│

├── screenshots/

│   ├── docker-installation.png

│   ├── docker-version.png

│   ├── docker-images.png

│   ├── running-containers.png

│   └── docker-hub.png

│

└── report/

    └── Docker_Practical_Report.pdf
    
### Topics Covered
Docker installation and verification
Docker images
Docker containers
Dockerfile
Docker volumes
Docker networks
Docker Compose
Docker Hub

### Application

A simple HTML web application is containerized using Nginx and served through a Docker container.

The application displays a welcome message and demonstrates how a static HTML application can be packaged and deployed using Docker.

1. Docker Installation

Docker Desktop was installed on Windows.

Official Docker Desktop installation guide:

https://docs.docker.com/desktop/setup/install/windows-install/

## Verify the Docker installation:

docker --version

Check Docker information:

docker info

### 2. Create the HTML Application

Create a file named:

index.html

Example:

<!DOCTYPE html>
<html>
<head>
    <title>Docker Practical Assignment</title>
</head>
<body>
    <h1>Welcome to My Docker Application</h1>
    <p>This application is running inside a Docker container.</p>
    <p>Created by Vimala Ankumpeta</p>
</body>
</html>

### 3. Create a Dockerfile

Create a file named exactly:

Dockerfile

Dockerfile contents:

FROM nginx:latest

COPY index.html /usr/share/nginx/html/index.html

EXPOSE 80

The Dockerfile uses the official Nginx image and copies the HTML application into the Nginx web root directory.

### 4. Build the Docker Image

Build the Docker image using:

docker build -t vimala-docker-app:1.0 .

Verify the image:

docker images

### 5. Run the Docker Container

Run the application using:

docker run -d --name vimala-web -p 8081:80 vimala-docker-app:1.0

The application can then be accessed at:

http://localhost:8081

Check running containers:

docker ps

Stop the container:

docker stop vimala-web

Remove the container:

docker rm vimala-web

### 6. Docker Volumes

Create a Docker volume:

docker volume create my-docker-volume

Run an Nginx container using the volume:

docker run -d --name volume-nginx -p 8082:80 -v my-docker-volume:/usr/share/nginx/html nginx

List Docker volumes:

docker volume ls

Inspect the volume:

docker volume inspect my-docker-volume

Docker volumes provide persistent storage that can exist independently of a container.

### 7. Create a Custom Docker Network

Create a custom Docker network:

docker network create my-docker-network

Check available networks:

docker network ls

Run two containers on the custom network:

docker run -d --name web1 --network my-docker-network nginx
docker run -d --name web2 --network my-docker-network nginx

The containers can communicate with each other through the Docker network.

Inspect the network:

docker network inspect my-docker-network

### 8. Docker Compose

The Docker Compose application contains:

Nginx web container
Redis container
Custom Docker network
Persistent Docker volume

The docker-compose.yml file defines the required services, network, volume, and port configuration.

Start the Compose application:

docker compose up -d --build

Check the Compose services:

docker compose ps

The web application is available at:

http://localhost:8083

Stop the Compose application:

docker compose down

### 9. Docker Hub

Docker Hub is used to store and share Docker images.

First, create a Docker Hub account and create a repository such as:

vimala-docker-app

Login to Docker Hub:

docker login

Tag the Docker image:

docker tag vimala-docker-app:1.0 YOUR_DOCKERHUB_USERNAME/vimala-docker-app:1.0

Example:

docker tag vimala-docker-app:1.0 ankumpetavimala/vimala-docker-app:1.0

Push the image to Docker Hub:

docker push ankumpetavimala/vimala-docker-app:1.0

Verify the local image:

docker images

The Docker image can then be accessed from the Docker Hub repository.

### 10. Useful Docker Commands

List Docker images:

docker images

List running containers:

docker ps

List all containers:

docker ps -a

List Docker volumes:

docker volume ls

List Docker networks:

docker network ls

Remove unused containers, networks, and images:

docker system prune

### 11. Screenshots

Screenshots demonstrating the practical work are included in the screenshots folder.

The screenshots cover:

Docker installation
Docker version verification
Docker images
Running containers
Docker Hub

### 12. Report

The complete practical assignment report is available in the report folder:

report/Docker_Practical_Report.pdf

## Conclusion

This practical assignment demonstrates the fundamentals of Docker, including creating Docker images, running containers, writing Dockerfiles, managing volumes and networks, using Docker Compose for multi-container applications, and publishing Docker images to Docker Hub.

Web Application - http://localhost:8080
