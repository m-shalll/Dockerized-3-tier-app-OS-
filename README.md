# Three-Tier Web Application

This project is a **3-tier web application** with frontend, backend, and database layers. The original application code was provided as part of an assignment, and my task was to **containerize the application using Docker** and orchestrate all services with Docker Compose for streamlined deployment.

---

## Project Overview

The application follows the classic **3-tier architecture**:

1. **Frontend** – User interface built with React, responsible for interacting with users.
2. **Backend** – API layer built with Node.js, handling business logic and communication with the database.
3. **Database** – MySQL, stores and manages the application data.

While the functional code was provided, the main challenge and learning objective of this assignment was to **write Dockerfiles for each layer** and ensure that the application runs consistently across isolated environments.

---

## Docker Implementation

The focus of this project was on creating **robust and efficient Dockerfiles** for each component:

### Frontend Dockerfile
- Copied `package.json` and `package-lock.json` first to leverage Docker’s **layer caching**.
- Installed dependencies separately before copying the full frontend source code.
- Built the frontend application inside the container.
- Exposed the appropriate port and used a lightweight web server (e.g., Nginx or Node) to serve the built files.

### Backend Dockerfile
- Started from an official Node.js or .NET base image.
- Copied `package.json` / project files first to cache dependency installation.
- Installed all dependencies and then copied the rest of the backend source code.
- Configured the container to run the backend server on startup.
- Exposed the API port for communication with the frontend.

### Database
- Used the official MySQL image.
- Configured environment variables for username, password, and database name.
- Initialized the database with provided scripts.

### Docker Compose
- Orchestrates all three services in a **single network** for seamless inter-container communication.
- Maps frontend, backend, and database ports to the host machine for easy access.
- Supports environment variables to configure the application without modifying code.
- Allows starting the entire application stack with a **single command**: `docker-compose up --build`

## Skills Demonstrated

- Writing efficient Dockerfiles for frontend and backend applications.

- Leveraging Docker layer caching to speed up build times.

- Configuring Docker Compose for multi-container orchestration.

- Managing environment variables and port mapping for inter-container communication.

- Understanding 3-tier architecture deployment in containers.
