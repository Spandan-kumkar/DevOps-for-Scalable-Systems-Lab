
# Assignment 5: Deployment and Scaling Using Kubernetes

## Aim
To deploy the containerized Student Task Manager web application on Kubernetes using Minikube, configure a Service, scale replicas, and verify application availability.

## Objectives
- Understand Kubernetes Deployments, Pods, and Services.
- Start and verify a local Kubernetes cluster using Minikube.
- Deploy a Dockerized application to Kubernetes.
- Expose the application using a NodePort Service.
- Scale the application replicas.
- Demonstrate Kubernetes self-healing by deleting a Pod.
- Verify application status and logs.

## Tools Used
- Docker Desktop
- Docker
- Kubernetes
- Minikube
- kubectl
- Visual Studio Code
- Web Browser

## Procedure
1. Verified the Docker image for the Student Task Manager application.
2. Started the Minikube cluster and checked its status.
3. Loaded the Docker image into Minikube.
4. Created a Kubernetes Deployment with two initial replicas.
5. Applied the Deployment configuration and verified the Pods.
6. Created a NodePort Service to expose the application.
7. Accessed the application through the Minikube Service.
8. Scaled the Deployment to four replicas.
9. Deleted a Pod to demonstrate Kubernetes self-healing.
10. Verified the recreated Pods and inspected application logs.

## Commands Used

```bash
# Verify Docker images
docker images

# Start and verify Minikube
minikube start
minikube status

# Verify the Kubernetes cluster
kubectl cluster-info
kubectl get nodes

# Load the Docker image into Minikube
minikube image load task-manager:1.0
minikube image ls

# Deploy the application
kubectl apply -f deployment.yaml
kubectl get deployments
kubectl get pods

# Expose the application
kubectl apply -f service.yaml
kubectl get svc

# Access the application
minikube service task-manager-service

# Get the service URL
minikube service task-manager-service --url

# Scale the Deployment to four replicas
kubectl scale deployment task-manager-deployment --replicas=4
kubectl get pods

# Demonstrate self-healing
kubectl delete pod <pod-name>
kubectl get pods

# Inspect Pod logs
kubectl logs <pod-name>

# Stop Minikube when finished
minikube stop
```

Replace `<pod-name>` with an actual Pod name returned by `kubectl get pods`.

## Kubernetes Configuration Files

- `deployment.yaml` — Defines the application Deployment, container image, port, and replica count.
- `service.yaml` — Defines the NodePort Service used to access the application.

## Expected Outcome
Successful deployment of the Student Task Manager application on Kubernetes, with service access, replica scaling, and self-healing demonstrated using Minikube.

## Screenshots
Add screenshots demonstrating:
- Minikube cluster status and nodes.
- Deployment and Service configuration files.
- Running application Pods.
- NodePort Service and application in the browser.
- Scaling to four replicas.
- Pod deletion and automatic recreation.
- Application Pod logs.


