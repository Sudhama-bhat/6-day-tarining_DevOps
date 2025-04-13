# 📘 DevOps Training - Day 4

## 🐳 Docker Project Deployment and Image Management

### 🛠️ Commands Executed:
```bash
git clone -b master https://github.com/Sudhama-bhat/Dimple-CapsuleProject.git
cd Dimple-CapsuleProject
docker build -t web-app-nodejs:1.0 .
docker images
docker inspect web-app-nodejs:1.0
docker run -td --name node-app -p 3015:3015 web-app-nodejs:1.0
docker ps
docker exec -it node-app /bin/bash
exit
docker login
docker tag web-app-nodejs:1.0 sudhamabhat/web-app-nodejs
docker push sudhamabhat/web-app-nodejs
docker run -td --name web-app1 -p 3015:3015 sudhamabhat/web-app-nodejs:latest
```

✅ **Assignment given and completed** with screenshots added to tasks.

---

## 🌍 Software Deployment Environments

- **Dev Environment**: For developers to test minimal functionality.
- **Testing Environment**: Used by testers for functional, performance, and load testing.
- **UAT (User Acceptance Test)**: Customers validate the prototype before release.
- **Production Environment**: Final deployment where customers access the live application.

---

## 🔍 Docker Concepts

### 🔹 Container:
A container is a lightweight, standalone executable package that includes everything needed to run a piece of software.

### 🔹 Dockerfile:
A text document containing instructions on how to build a Docker image.

### 🔹 Docker Image:
A template containing code, dependencies, config, and platform info. Think: **Build Once, Run Anywhere.**

### 🔹 Docker Hub:
A public/private image repository used to store Docker images.

### Workflow:
```plaintext
Developer -> Docker File -> Docker Image -> Docker Hub -> Staging Environment
```

---

## 🧪 Important Docker Commands
```bash
docker ps -a           # List all containers (running + stopped)
docker ps              # List running containers
docker create -it --name webserver amazonlinux /bin/bash
docker exec -it webserver /bin/bash
exit                   # Stops and exits container

docker run -it --name sample ubuntu /bin/bash   # Create + run container interactively
# Detach from container but keep running:
Ctrl + P + Q

docker run -td --name web-app -p 3002:3000 muralisocial123/cart-page-test:1.0
```

---

## 📦 Dockerfile Instructions

### 🛠️ Build Phase:
- `FROM` – Base image
- `COPY` – Copy files from local to image
- `ADD` – Copy + download files from web
- `RUN` – Install packages
- `.dockerignore` – Exclude files from build context

### ▶️ Run Phase:
- `CMD` – Code to execute in container (allows runtime args)
- `ENTRYPOINT` – Main entry point (does NOT allow runtime args)
- `EXPOSE` – Define port
- `ENV` – Set environment variables
- `WORKDIR` – Set working directory in image
- `USER` – Define user

### ✅ Required Info from Dev Team:
- Environment variables
- Port numbers
- DB endpoints

---

## 📋 Dockerfile Creation Checklist
1. Define base image
2. Create working directory
3. Copy dependencies
4. Install dependencies
5. Copy entire source code
6. Define port
7. Set entrypoint/CMD to run the app

---

## 📁 Example Workflow Recap:
```bash
git clone -b master https://github.com/Sudhama-bhat/Dimple-CapsuleProject.git
cd Dimple-CapsuleProject
docker build -t web-app-nodejs:1.0 .
docker images
docker inspect web-app-nodejs:1.0
docker run -td --name node-app -p 3015:3015 web-app-nodejs:1.0
docker tag web-app-nodejs:1.0 sudhamabhat/web-app-nodejs
docker push sudhamabhat/web-app-nodejs
```

### 📌 Assignment:
1. Create a web project and write Dockerfile for NGINX deployment.
2. Identify container issues.

---

*End of Day 4 Notes*

