# Dockerfile for React Application

# Step 1: Use an official Node.js runtime as a parent image
FROM node:18-alpine AS builder

# Step 2: Set the working directory in the container
WORKDIR /app

# Step 3: Copy package.json and package-lock.json
COPY package*.json ./

# Step 4: Install dependencies
RUN npm install

# Step 5: Copy the rest of the application files
COPY . .

# Step 6: Build the React app
RUN npm run build

# Step 7: Use Nginx to serve the build files
FROM nginx:alpine

# Step 8: Copy the build files from the previous stage
COPY --from=builder /app/build /usr/share/nginx/html

# Step 9: Expose port 80
EXPOSE 80

# Step 10: Start Nginx
CMD ["nginx", "-g", "daemon off;"]

