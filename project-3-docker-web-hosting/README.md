# Project 3 - Docker Web Hosting

## Project Overview

Built and deployed a simple website using Docker.

The website is packaged into a Docker image using a Dockerfile and then run inside a Docker container using Nginx.

## Architecture

Website Files
    |
    v
Dockerfile
    |
    | docker build
    v
Docker Image
    |
    | docker run
    v
Docker Container
    |
    v
Nginx
    |
    v
Browser
localhost:8080

## Technologies Used

- Docker
- Dockerfile
- Nginx
- Docker Images
- Docker Containers
- Docker Volumes
- Docker Networks
- Docker CLI

## Implementation

1. Created a simple HTML website.
2. Created a Dockerfile using the Nginx base image.
3. Built a Docker image named `my-docker-website`.
4. Created a container named `my-website`.
5. Mapped host port 8080 to container port 80.
6. Accessed the website through `http://localhost:8080`.
7. Created a Docker volume named `website-data`.
8. Tested persistent data using the Docker volume.
9. Created a Docker network named `my-network`.
10. Connected multiple containers to the network.
11. Tested communication between containers using container names and `curl`.

## Dockerfile

The Dockerfile uses Nginx as the base image and copies the website's `index.html` into the Nginx web directory.

## Port Mapping

The container's Nginx web server listens on port 80.

The host exposes port 8080.

8080:80

This means:

Host port 8080
        |
        v
Container port 80

## Docker Volume

A volume named `website-data` was created to demonstrate persistent storage.

Data stored in the volume remained available when accessed from a different container.

## Docker Network

A custom Docker network named `my-network` was created.

Two containers were connected to the network and communication was tested using:

curl http://container-a

This demonstrated Docker's internal container-to-container networking and DNS-based service discovery.

## Container Troubleshooting

Useful commands practiced:

docker ps
docker ps -a
docker images
docker logs <container>
docker inspect <container>
docker exec -it <container> /bin/bash
docker network ls
docker network inspect <network>
docker volume ls

## Key Concepts Learned

- Docker
- Docker images
- Docker containers
- Dockerfile
- Nginx
- Port mapping
- Docker volumes
- Persistent storage
- Docker networks
- Container-to-container communication
- Docker troubleshooting
