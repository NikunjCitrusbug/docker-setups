# Django + Celery with Docker

## 🚀 Setup Instructions

### 1️⃣ Prerequisites
- Install [Docker](https://docs.docker.com/get-docker/) and [Docker Compose](https://docs.docker.com/compose/install/)
- Ensure you have a `requirements.txt` file with Django, Celery, and Redis dependencies
- Set up an **RDS PostgreSQL** instance and update your `.env` file with:
  ```sh
  DATABASE_URL=postgres://user:password@your-rds-endpoint:5432/yourdatabase
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

### 6️⃣ Verify Celery Worker
Run the following command to check Celery logs:
```sh
docker logs celery_worker
```

### 7️⃣ Stopping the Services
```sh
docker-compose down
```
