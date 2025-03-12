# Django Application with Celery (Worker and Beat) using Docker

This repository contains a Django application with Celery worker and Celery beat, containerized using Docker. Environment variables are managed using a `.env` file for easy configuration.

---

## **Table of Contents**
1. [Prerequisites](#prerequisites)
2. [Project Structure](#project-structure)
3. [Setup Instructions](#setup-instructions)
   - [Create a `.env` File](#1-create-a-env-file)
   - [Build and Start the Services](#2-build-and-start-the-services)
   - [Access the Django Application](#3-access-the-django-application)
   - [Monitor Celery Worker and Beat](#4-monitor-celery-worker-and-beat)
   - [Stop the Services](#5-stop-the-services)
4. [Troubleshooting](#troubleshooting)

---

## **Prerequisites**
Before you begin, ensure you have the following installed on your machine:
- **Docker**: [Install Docker](https://docs.docker.com/get-docker/)
- **Docker Compose**: [Install Docker Compose](https://docs.docker.com/compose/install/)

---

## **Project Structure**
```
Here’s the structure of the project:
├── Dockerfile # Dockerfile for the Django app and Celery
├── docker-compose.yml # Docker Compose file to orchestrate services
├── .env # Environment variables for the project
├── requirements.txt # Python dependencies for Django and Celery
├── myproject/ # Django project directory
│ ├── settings.py # Django settings file
│ ├── celery.py # Celery configuration file
│ └── ... # Other Django project files
└── README.md # This README file
```


---

## **Setup Instructions**

### **1. Create a `.env` File**
Create a `.env` file in the root of your project and add the following environment variables:

```env
# Django Settings
DEBUG=1
SECRET_KEY=your-secret-key
ALLOWED_HOSTS=localhost,127.0.0.1

# Celery Settings
CELERY_BROKER_URL=redis://redis:6379/0
CELERY_RESULT_BACKEND=redis://redis:6379/0
```

### **2. Build and Start the Services**

Run the following command to build and start all services (Django app, Celery worker, Celery beat, and Redis):

```bash 
docker-compose up -d
```

This will:

Build the Docker image for the Django app and Celery.

Start the Django app on port 8000.

Start the Celery worker and Celery beat.

Start a Redis container for Celery's message broker.


### **3. Build and Start the Services**

Once the services are running, open your browser and go to:

```bash
http://localhost:8000
```

### **4. Monitor Celery Worker and Beat**
To monitor the Celery worker and beat, check their logs:

##### Celery Worker Logs:
```bash
docker logs celery_worker
```
##### Celery Beat Logs:
```bash 
docker logs celery_beat
```
### **5. Stop the Services**
To stop all services, run:
```bash
docker-compose down
```
This will stop and remove all containers.



## **Troubleshooting**

### **1. Services Not Starting**
If a service fails to start, check its logs:
```bash
docker logs <container_name>
```
Replace <container_name> with the name of the container (e.g., django_app, celery_worker, celery_beat, or redis).

### **2. Port Conflicts**
Ensure ports 8000 (Django) and 6379 (Redis) are not already in use. You can change the ports in the docker-compose.yml file if needed.

### **3. Missing Environment Variables**
Ensure all required environment variables are defined in the .env file. Missing variables may cause the application to fail.

---

### **How to Use**
1. Place the `Dockerfile`, `docker-compose.yml`, `.env`, and `README.md` in your Django project's root directory.
2. Add a `requirements.txt` file with your Django app's dependencies (e.g., `Django`, `celery`, `redis`).
3. Configure Celery in your Django app (e.g., create `celery.py` in your project directory).
4. Follow the instructions in the `README.md` to build and run the containers.

---

