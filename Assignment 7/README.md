# Assignment 7: Monitoring with Prometheus

## Aim
To set up Prometheus to collect and monitor application performance metrics of the Student Task Manager in real time.

## Objectives
- Configure application metrics using Prometheus.
- Expose metrics through the `/metrics` endpoint.
- Deploy Prometheus on Kubernetes using Minikube.
- Configure Prometheus to scrape application metrics.
- Verify application availability through Prometheus Targets.
- Execute PromQL queries to monitor HTTP requests and memory usage.

## Tools Used
- Node.js and npm
- Prometheus
- prom-client
- Docker
- Kubernetes
- Minikube
- kubectl
- Git and GitHub

## Procedure

1. Install the Prometheus client library using `npm install prom-client`.
2. Modify `app.js` to enable default Node.js metrics and create an HTTP request counter.
3. Add middleware to count HTTP requests and expose metrics through the `/metrics` endpoint.
4. Start the application and verify metrics at `http://localhost:3000/metrics`.
5. Build a new Docker image containing the updated application.
6. Load the image into Minikube and update the Kubernetes Deployment.
7. Create `prometheus.yml` with a scrape interval of 5 seconds and the application Service as the target.
8. Create a Kubernetes ConfigMap from the Prometheus configuration.
9. Create and deploy the Prometheus Deployment and Service.
10. Access Prometheus using `minikube service prometheus-service`.
11. Navigate to **Status → Targets** and verify that the `task-manager` target is `UP`.
12. Execute PromQL queries to inspect application availability, HTTP requests, request rate, and memory usage.
13. Generate application traffic and observe changes in the metrics.

## Commands Used

### Install Dependencies
```bash
npm install prom-client
npm install
npm start
```

### Build and Load Docker Image
```bash
docker build -t task-manager:2.0 .
minikube image load task-manager:2.0
kubectl apply -f deployment.yaml
kubectl get pods
```

### Configure and Deploy Prometheus
```bash
kubectl create configmap prometheus-config --from-file=prometheus.yml
kubectl apply -f prometheus-deployment.yaml
kubectl apply -f prometheus-service.yaml
kubectl get pods
kubectl get services
minikube service prometheus-service
```

If the ConfigMap already exists, update it instead of running the create command again.

### PromQL Queries

Check application availability:
```promql
up{job="task-manager"}
```

View total HTTP requests:
```promql
task_manager_http_requests_total
```

Calculate HTTP request rate:
```promql
rate(task_manager_http_requests_total[1m])
```

Monitor process memory:
```promql
process_resident_memory_bytes
```

Monitor Node.js heap memory:
```promql
nodejs_heap_size_used_bytes
```

## Expected Outcome

- Application metrics are available through `/metrics`.
- Prometheus successfully collects application metrics.
- The `task-manager` target appears as `UP`.
- PromQL queries display HTTP request and memory metrics.
- Changes in application traffic are reflected in the request counter.

## Screenshots
Include screenshots of:
- The `/metrics` endpoint.
- Updated Docker image and running Kubernetes pods.
- Prometheus pods and Service.
- Prometheus Targets showing `task-manager` as `UP`.
- PromQL query results.
- HTTP request counter changing after generating application traffic.

