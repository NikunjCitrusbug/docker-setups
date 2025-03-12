# 🚀 NestJS Application with Docker

## 📌 Prerequisites
- Install [Docker](https://docs.docker.com/get-docker/)
- Ensure your project has a valid `package.json` and an `app.module.ts` entry point.

## 🔹 Build and Run the Container

### 1️⃣ **Build the Docker Image**
```sh
docker build -t nest_app .
```

### 2️⃣ **Run the Container**
```sh
docker run -d -p 3000:3000 --name nest_app nest_app
```

### 3️⃣ **Access the API**
- Open your browser: [http://localhost:3000](http://localhost:3000)

## 🔍 Debugging and Logs

### 🔹 **View Logs**
```sh
docker logs -f nest_app
```

### 🔹 **Access Running Container**
```sh
docker exec -it nest_app sh
```

## 📌 Stopping & Removing Containers

### 🔹 **Stop the Container**
```sh
docker stop nest_app
```

### 🔹 **Remove the Container**
```sh
docker rm nest_app
```

## 🔄 Rebuild After Code Changes
```sh
docker build -t nest_app . && docker run -d -p 3000:3000 --name nest_app nest_app
```

## 🔥 Running in Development Mode (with Live Reload)
If you want **hot-reloading** using `nodemon`, update your `Dockerfile` to install it and mount your project as a volume:

```sh
docker run -d -p 3000:3000 -v $(pwd):/app --name nest_app nest_app
```

## ⚙️ Using Environment Variables
Pass environment variables while running the container:
```sh
docker run -d -p 3000:3000 --name nest_app --env NODE_ENV=production nest_app
```

