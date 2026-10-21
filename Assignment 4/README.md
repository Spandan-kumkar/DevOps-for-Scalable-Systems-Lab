
# Assignment 4: Dockerization of Student Task Manager

## Aim
To containerize the Student Task Manager web application using Docker so that it can run consistently across different environments.

## Objectives
- Understand Docker images and containers.
- Create a Dockerfile for the application.
- Build a Docker image.
- Run the application inside a Docker container.
- Manage container lifecycle operations.
- Verify application accessibility through a browser.

## Tools Used
- Docker
- Docker Desktop
- Node.js
- npm
- Visual Studio Code

## Procedure
1. Verified the Docker installation.
2. Created a `Dockerfile` using the Node.js base image.
3. Configured the application working directory and dependencies.
4. Exposed port `3000` for application access.
5. Created a `.dockerignore` file to exclude unnecessary files.
6. Built the Docker image with the tag `task-manager:1.0`.
7. Ran a container and mapped port `3000` to the host.
8. Checked the running container and application logs.
9. Stopped, restarted, and removed the container to demonstrate container lifecycle management.
10. Verified the application in a web browser at `http://localhost:3000`.

## Dockerfile

```dockerfile
FROM node:20-alpine
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
EXPOSE 3000
CMD ["npm", "start"]
```

## .dockerignore

```text
node_modules
.git
.gitignore
README.md
```

## Commands Used

```bash
# Check Docker installation
docker --version
docker info

# Build the Docker image
docker build -t task-manager:1.0 .

# List available images
docker images

# Run the container
docker run -d -p 3000:3000 --name task-manager-container task-manager:1.0

# Check running containers
docker ps

# View container logs
docker logs task-manager-container

# Stop and restart the container
docker stop task-manager-container
docker start task-manager-container

# Stop and remove the container
docker stop task-manager-container
docker rm task-manager-container

# List all containers
docker ps -a
```

## Expected Outcome
Successful containerization of the Student Task Manager application and verification that it runs inside a Docker container.

## Screenshots
Add screenshots demonstrating:
- Docker version and installation.
- Dockerfile and `.dockerignore`.
- Successful Docker image build.
- Docker image listing.
- Running container and port mapping.
- Application running in the browser.
- Container logs and lifecycle operations.

## Repository
[Student Task Manager GitHub Repository](<YOUR-GITHUB-REPOSITORY-URL>)
