# Kubernetes Setup and Deployment Guide 🌐🚀

## Overview 📝

This repository contains a comprehensive guide and step-by-step instructions for setting up and managing Kubernetes clusters, deploying applications, and understanding core Kubernetes concepts and commands. The following instructions cover Day 1 to Day 6 of the process, starting from the setup of Docker and Kubernetes, to managing namespaces, pods, deployments, and services.

---

## Table of Contents 📑

1. [Day 1: Docker Introduction & Setup](#day-1-docker-introduction-setup)
2. [Day 2: Dockerfile Creation and Deployment](#day-2-dockerfile-creation-deployment)
3. [Day 3: Docker Hub and Deployment](#day-3-docker-hub-and-deployment)
4. [Day 4: Kubernetes Introduction](#day-4-kubernetes-introduction)
5. [Day 5: Managing Kubernetes Resources](#day-5-managing-kubernetes-resources)
6. [Day 6: Advanced Kubernetes Concepts](#day-6-advanced-kubernetes-concepts)

---

## Day 1: Docker Introduction & Setup 🐳

In this section, you will set up Docker and get familiar with basic commands.

### Key Commands:
```bash
# Build Docker Image
docker build -t web-app-nodejs:1.0 .

# Run Docker Container
docker run -td --name node-app -p 3015:3015 web-app-nodejs:1.0

# Check Running Containers
docker ps

# Inspect Docker Image Layers
docker inspect web-app-nodejs:1.0
