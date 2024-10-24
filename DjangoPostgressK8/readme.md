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
