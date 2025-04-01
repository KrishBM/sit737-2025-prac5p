# SIT737 - Cloud Native Application Development
## 5.1P: Containerisation of a Simple Web Application using Docker

This repository contains a simple Node.js web application that has been containerized using Docker as part of the SIT737/SIT323 Cloud Native Application Development unit.

## Project Overview

The project involves creating a Docker image for a basic web application, configuring it with the necessary dependencies, and implementing container health checks to ensure application reliability. The application is a simple form that accepts a user's name and responds with a greeting.

## Prerequisites

To run this project, you'll need the following tools installed:

- [Git](https://github.com)
- [Visual Studio Code](https://code.visualstudio.com/) (or any preferred code editor)
- [Node.js](https://nodejs.org/en/download/)
- [Docker](https://www.docker.com/products/docker-desktop)

## Application Structure

- `index.js` - Main application file containing the Express.js server code
- `package.json` - Node.js project configuration file
- `Dockerfile` - Instructions for building the Docker image
- `docker-compose.yml` - Configuration for Docker Compose, including health checks

## Application Code

The application is a simple Express.js server that:
1. Serves a form at the root URL where users can enter their name
2. Accepts form submissions via POST to '/submit'
3. Responds with a personalized greeting

## How to Run the Application

### Local Development

1. Clone the repository:
```bash
git clone https://github.com/your-username/sit737-2025-prac5p.git
cd sit737-2025-prac5p
```

2. Install dependencies:
```bash
npm install
```

3. Run the application:
```bash
node index.js
```

4. Access the application at http://localhost:3000

### Using Docker

1. Build the Docker image:
```bash
docker build -t webapp .
```

2. Run the container:
```bash
docker run -p 3000:3000 webapp
```

### Using Docker Compose

1. Start the Docker Compose environment:
```bash
docker-compose up
```

2. Access the application at http://localhost:3000

## Container Health Check

The Docker Compose file includes a health check configuration that:
- Tests the application every 30 seconds
- Times out after 10 seconds
- Retries up to 3 times before considering the container unhealthy
- Automatically restarts the container if it becomes unhealthy

To check the health status of your container:
```bash
docker ps
```

For more detailed health check information:
```bash
docker inspect <container_id> | grep -A 10 Health
```

## Pushing to Docker Hub

1. Log in to Docker Hub:
```bash
docker login
```

2. Tag your image:
```bash
docker tag webapp <your-username>/webapp
```

3. Push the image to Docker Hub:
```bash
docker push <your-username>/webapp
```

## Assignment Details

This project was created as part of SIT737/SIT323 Cloud Native Application Development 5.1P assessment, which required:

1. Installing Docker
2. Creating a simple web application
3. Creating a Dockerfile
4. Building a Docker image
5. Creating a Docker Compose file with health checks
6. Testing the application
7. Pushing the Docker image to a registry

## Author

KrishBM

## Repository

[https://github.com/KrishBM/sit737-2025-prac5p](https://github.com/KrishBM/sit737-2025-prac5p)
