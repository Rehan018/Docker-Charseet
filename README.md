```bash
# Docker Commands A to Z

# A - Attach to a running container
docker attach <container_id>

# B - Build an image from a Dockerfile
docker build -t <image_name> <path_to_Dockerfile>

# C - Create a new container
docker create <image_name>

# D - Delete one or more containers
docker rm <container_id>

# E - Execute a command in a running container
docker exec -it <container_id> <command>

# F - Fetch the logs of a container
docker logs <container_id>

# G - Get detailed information about a container
docker inspect <container_id>

# H - Help: Get help on Docker commands
docker --help

# I - Inspect changes on a container's file system
docker diff <container_id>

# J - Join a network to a running container
docker network connect <network_name> <container_id>

# K - Kill a running container
docker kill <container_id>

# L - List images
docker images

# M - Monitor Docker events
docker events

# N - Network: Manage Docker networks
docker network <subcommand>

# O - Overview of Docker resources
docker stats

# P - Push an image to a registry
docker push <image_name>

# Q - Quit and detach from a container
Ctrl + P, Ctrl + Q (detach)

# R - Remove one or more images
docker rmi <image_id>

# S - Start a stopped container
docker start <container_id>

# T - Tag an image into a repository
docker tag <image_id> <repository_name>:<tag>

# U - Unpause a paused container
docker unpause <container_id>

# V - View Docker system information
docker info

# W - Watch container resource usage
docker stats <container_id>

# X - Execute a command in a new container
docker run <image_name> <command>

# Y - YAML: Compose a multi-container application
docker-compose -f <docker-compose-file> up

# Z - Zip: Save an image to a tar archive file
docker save -o <output_file>.tar <image_name>
```

```html
### Explanation:
- Each command is represented with a brief description of its functionality.
- Replace `<placeholders>` with actual names or IDs as per your Docker setup.
- These commands cover a wide range of Docker functionalities, from managing containers and images to networking, logging, and system information.
```




```js
##Dockerfile for Node JS
# Use an official Node.js runtime as a parent image

FROM node:14

# Set the working directory in the container
WORKDIR /usr/src/app


# Copy package.json and package-lock.json to the working directory
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the application code to the working directory
COPY . .

# Expose port 3000 to the outside world
EXPOSE 3000

# Command to run the application
CMD ["npm", "start"]

docker build -t my-node-app .

docker run -p 3000:3000 my-node-app
```


```html
Verify and Test:
```
   ```bash
   Open a web browser and navigate to http://localhost:3000 (or the port you specified) to verify that your application is running correctly inside the Docker container.
   ```

1. **Create a Dockerfile**:
   Create a new file named `Dockerfile` (without any file extension) in your project directory.

   ```bash
   touch Dockerfile
   ```

2. **Edit Dockerfile**:
   Open `Dockerfile` in a text editor and add the following instructions:

   ```Dockerfile
   # Use an official Node.js runtime as a parent image
   FROM node:14

   # Set the working directory in the container
   WORKDIR /usr/src/app

   # Copy package.json and package-lock.json to the working directory
   COPY package*.json ./

   # Install dependencies
   RUN npm install

   # Copy the rest of the application code to the working directory
   COPY . .

   # Expose port 3000 to the outside world
   EXPOSE 3000

   # Command to run the application
   CMD ["npm", "start"]
   ```

3. **Build the Docker Image**:
   Now, build the Docker image using the `docker build` command. Make sure you are in the directory where your Dockerfile is located.

   ```bash
   docker build -t my-node-app .
   ```

   - `-t my-node-app`: Tags your image with the name `my-node-app` for easy reference.
   - `.`: Specifies the build context as the current directory.

4. **Run a Container from the Image**:
   Once the image is built, you can run a container based on it:

   ```bash
   docker run -p 3000:3000 my-node-app
   ```

   - `-p 3000:3000`: Maps port 3000 of the host machine to port 3000 inside the container, allowing access to your Node.js application.
   - `my-node-app`: The name of the Docker image to use.

5. **Access Your Application**:
   Open a web browser and navigate to `http://localhost:3000` to see your Node.js application running inside the Docker container.
