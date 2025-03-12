# FastAPI Application with Docker

## 🚀 Setup Instructions

### 1️⃣ Prerequisites
- Install [Docker](https://docs.docker.com/get-docker/)
- Ensure you have a `requirements.txt` file with FastAPI and Uvicorn:
  ```sh
  fastapi
  uvicorn
  ```

### 2️⃣ Build and Run the Container
#### 🔹 Build the Docker Image
```sh
docker build -t fastapi_app .
```

#### 🔹 Run the Container
```sh
docker run -d -p 8000:8000 --name fastapi_app fastapi_app
```

### 3️⃣ Access the API
- Open your browser and go to: [http://localhost:8000](http://localhost:8000)
- Swagger Docs: [http://localhost:8000/docs](http://localhost:8000/docs)

### 4️⃣ Stopping the Container
```sh
docker stop fastapi_app
```

### 5️⃣ Removing the Container
```sh
docker rm fastapi_app
```

This setup ensures a **minimal and efficient** FastAPI deployment with Docker. Let me know if you need any modifications! 🚀