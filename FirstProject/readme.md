# Django Kubernetes Deployment

## Project Overview

In this project, the Docker container `pamblo/django-app:v2` is automatically loaded in the deployment, configuring a fully functional Django server. The setup ensures high availability and stability by utilizing Kubernetes features.

### Steps to Follow

1. **Deployment Configuration**:
   - The deployment already includes the Docker container setup. You can review the configuration in the `Deployment.yaml` file, which specifies the use of **3 replica sets**, ensuring redundancy and fault tolerance.

2. **Service Configuration**:
   - A service is linked to the deployment for external access, and its configuration can be found in the `services.yaml` file.

3. **Expose the Port**:
   Once the deployment is created, expose the port to access the Django server using the following command:
   ```bash
   kubectl port-forward "Name-of-deployment" 8000:8000
