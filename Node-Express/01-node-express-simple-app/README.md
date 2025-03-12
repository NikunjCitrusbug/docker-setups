# Node.js Express Application with Docker

## 🚀 Setup Instructions

### 1️⃣ Prerequisites
- Install [Docker](https://docs.docker.com/get-docker/)
- Ensure you have a `package.json` file with required dependencies.
- Your application should have an entry point like `server.js` or `app.js`.

### 2️⃣ Build and Run the Container
#### 🔹 Build the Docker Image
```sh
docker build -t node_app .
```

#### 🔹 Run the Container
```sh
docker run -d -p 3000:3000 --name node_app node_app
```

### 3️⃣ Access the API
- Open your browser and go to: [http://localhost:3000](http://localhost:3000)

### 4️⃣ Debugging and Logs
#### 🔹 View Container Logs
```sh
docker logs -f node_app
```

#### 🔹 Access Running Container
```sh
docker exec -it node_app sh
```

#### 🔹 Restart the Container
```sh
docker restart node_app
```

### 5️⃣ Stopping and Removing the Container
#### 🔹 Stop the Container
```sh
docker stop node_app
```

#### 🔹 Remove the Container
```sh
docker rm node_app
```

### 6️⃣ Rebuilding the Container (After Code Changes)
```sh
docker build -t node_app . && docker run -d -p 3000:3000 --name node_app node_app
```

### 7️⃣ Running in Development Mode
If you want to enable hot-reloading with `nodemon`, update your `Dockerfile` to install it and mount the volume:

#### 🔹 Updated Run Command (for Development)
```sh
docker run -d -p 3000:3000 -v $(pwd):/app --name node_app node_app
```

### 8️⃣ Environment Variables
You can pass environment variables using the `--env` flag:
```sh
docker run -d -p 3000:3000 --name node_app --env NODE_ENV=production node_app
```
