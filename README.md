# Kubernetes and Docker Exercises

This repository showcases two Docker and Kubernetes deployment exercises for Django applications. Each exercise increases in complexity, demonstrating key skills in container orchestration.

## 1. **Basic Deployment: Django App**

### Overview
This project demonstrates how to deploy a simple Django application in Kubernetes using Docker. It involves creating a Docker image, pushing it to Docker Hub, and deploying it using a Kubernetes `Deployment` and `Service`.

### Key Steps
- Build a Docker image for a Django project.
- Push the Docker image to Docker Hub.
- Create Kubernetes objects:
  - Deployment for Django.
  - LoadBalancer service to expose the application.
- Use `kubectl port-forward` for local access if necessary.

### Commands
- Build Docker image:
  docker build -t <yourPath> .   #IMPORTANT FINALL DOT
  docker push <yourPath>
- Apply kubernetes config:
  kubectl apply -f deployment.yaml
  kubectl apply -f loadbalancer-service.yaml

## 2. **Intermediate Deployment: Django + PostgreSQL**

### Overview
This exercise connects a Django application to a PostgreSQL database, both managed within a Kubernetes cluster. The setup uses Docker containers for both services and Kubernetes StatefulSets for persistent PostgreSQL storage.

### Key Steps
- Create a Docker image for Django, configured to use PostgreSQL.
- Set up a PostgreSQL database in Kubernetes with a StatefulSet.
- Deploy both the Django app and PostgreSQL using Kubernetes.
- Expose the Django service using a LoadBalancer or NodePort.

### Kubernetes Objects
- **Django Deployment**: Runs the Django application using the Docker image.
- **PostgreSQL StatefulSet**: Provides persistent database storage.
- **Service**: LoadBalancer or NodePort to expose Django.

### Commands
- Build Docker image:
  docker build -t <yourPath> . #IMPORTANT FINALL DOT
  docker push <yourPath>
- Apply kubernetes config:
  kubectl apply -f postgres-statefulset.yaml
  kubectl apply -f deployment.yaml
  kubectl apply -f loadbalancer-service.yaml

