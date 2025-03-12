# Simple Django Application with Docker

This repository contains a simple Django application containerized using Docker. The application runs on port `8000`.

## Prerequisites
- Docker installed on your machine.

## Setup Instructions

### 1. Build the Docker Image
Run the following command to build the Docker image:
```bash
docker build -t django-app .

```
### 2.  To run the Docker Image
Run the following command to run the docker image:
```bash
docker run -d -p 8000:8000 django-app
```

### 3. To check logs
Run the following command to check the logs:
```bash
docker ps
docker logs <container_id>
```

### **How to Use**
1. Place the `Dockerfile` and `README.md` in your Django project's root directory.
2. Add a `requirements.txt` file with your Django app's dependencies (e.g., `Django`).
3. Follow the instructions in the `README.md` to build and run the container.

