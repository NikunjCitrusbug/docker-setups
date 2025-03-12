# 🚀 React Application with Docker

## 📌 Prerequisites
- Install [Docker](https://docs.docker.com/get-docker/)
- Ensure your project has a `package.json` and `src/index.js` or `src/main.jsx`

## 🔹 Build and Run the Container

### 1️⃣ **Build the Docker Image**
```sh
docker build -t react_app .
```

### 2️⃣ **Run the Container**
```sh
docker run -d -p 3000:3000 --name react_app react_app
```

### 3️⃣ **Access the Application**
- Open your browser: [http://localhost:3000](http://localhost:3000)

## 🔍 Debugging and Logs

### 🔹 **View Logs**
```sh
docker logs -f react_app
```

### 🔹 **Access Running Container**
```sh
docker exec -it react_app sh
```

## 📌 Stopping & Removing Containers

### 🔹 **Stop the Container**
```sh
docker stop react_app
```

### 🔹 **Remove the Container**
```sh
docker rm react_app
```

## 🔄 Rebuild After Code Changes
```sh
docker build -t react_app . && docker run -d -p 3000:3000 --name react_app react_app
```

## 🔥 Running in Development Mode (with Live Reload)
If you want **hot-reloading**, mount your project as a volume:

```sh
docker run -d -p 3000:3000 -v $(pwd):/app --name react_app react_app
```

## ⚙️ Using Environment Variables
Pass environment variables while running the container:
```sh
docker run -d -p 3000:3000 --name react_app --env NODE_ENV=production react_app
```

---

This setup ensures an **efficient and production-ready** deployment for your React application. 🚀 Let me know if you need any modifications! 😊

