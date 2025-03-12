# Django + Celery Worker with Docker

## 🚀 Setup Instructions

### 1️⃣ Prerequisites
- Install [Docker](https://docs.docker.com/get-docker/) and [Docker Compose](https://docs.docker.com/compose/install/)
- Ensure you have a `requirements.txt` file with Django, Celery, and Redis dependencies
- Create a `.env` file with:
  ```sh
  DATABASE_URL=postgres://user:password@your-rds-endpoint:5432/yourdatabase
  CELERY_BROKER_URL=redis://redis:6379/0
  CELERY_RESULT_BACKEND=redis://redis:6379/0
  DEBUG=True
  ```

### 2️⃣ Build and Run the Containers
```sh
# Build the containers
docker-compose build

# Start the services
docker-compose up -d
```

### 3️⃣ Run Database Migrations
```sh
docker-compose exec django python manage.py migrate
```

### 4️⃣ Create a Superuser (Optional)
```sh
docker-compose exec django python manage.py createsuperuser
```

### 5️⃣ Access the Django App
Open your browser and visit: `http://localhost:8000`

### 6️⃣ Verify Celery Worker and Celery Beat
Run the following command to check Celery Worker logs:
```sh
docker logs celery_worker
```
Run the following command to check Celery Beat logs:
```sh
docker logs celery_beat
```

### 7️⃣ Stopping the Services
```sh
docker-compose down
```
