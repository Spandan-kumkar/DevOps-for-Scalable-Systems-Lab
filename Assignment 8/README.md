# Assignment 8: Visualization of Real-Time Application Metrics Using Grafana

## Aim
To configure Grafana dashboards for visualizing and analyzing real-time application performance metrics collected by Prometheus.

## Objectives
- Deploy Grafana on Kubernetes.
- Access the Grafana web interface.
- Configure Prometheus as a Grafana data source.
- Create a monitoring dashboard for the Student Task Manager.
- Visualize application availability, HTTP request metrics, and memory usage.
- Use PromQL queries to analyze application performance.
- Generate application traffic and observe real-time dashboard updates.

## Tools Used
- Grafana
- Prometheus
- Docker
- Kubernetes
- Minikube
- kubectl
- Web Browser
- Student Task Manager Application

## Procedure

1. Ensure the Student Task Manager application and Prometheus are running from Assignment 7.
2. Deploy Grafana on Kubernetes.
3. Verify that the Grafana pod is running.
4. Expose Grafana through a Kubernetes Service.
5. Open the Grafana web interface.
6. Configure Prometheus as the data source using the Prometheus service URL.
7. Create a new dashboard named **Student Task Manager Monitoring Dashboard**.
8. Create an application availability panel using the query `up{job="task-manager"}`.
9. Create an HTTP request rate panel using the query `sum(rate(task_manager_http_requests_total[1m]))`.
10. Create a process memory usage panel using the query `process_resident_memory_bytes`.
11. Create a Node.js heap memory panel using the query `nodejs_heap_size_used_bytes`.
12. Save the dashboard and generate application traffic.
13. Observe the real-time changes in the dashboard panels.

## Commands Used

### Deploy Grafana

If Grafana is already deployed from your earlier monitoring setup, verify it first:

```bash
kubectl get pods -n monitoring
kubectl get services -n monitoring
```

If your existing Grafana deployment is in the `monitoring` namespace, access it using:

```bash
kubectl port-forward -n monitoring service/grafana 3000:80
```

Keep this terminal running and open:

`http://localhost:3000`

> If your Grafana Service uses a different name or port, use the values shown by `kubectl get services -n monitoring`.

### Verify Prometheus

```bash
kubectl get pods
kubectl get services
```

Ensure Prometheus and the Student Task Manager application are running.

## Grafana Configuration

### 1. Configure Prometheus Data Source

In Grafana:

1. Open **Connections → Data sources**.
2. Select **Add data source**.
3. Choose **Prometheus**.
4. Enter the Prometheus service URL accessible from Grafana.
5. Click **Save & test** and verify the connection.

### 2. Create the Dashboard

Create a dashboard with the name:

**Student Task Manager Monitoring Dashboard**

Add the following panels.

### Panel 1: Application Status

PromQL query:

```promql
up{job="task-manager"}
```

Visualization: **Stat**

Panel title: `Application Status`

A value of `1` indicates that Prometheus can scrape the application target successfully.

### Panel 2: HTTP Request Rate

PromQL query:

```promql
sum(rate(task_manager_http_requests_total[1m]))
```

Visualization: **Time series**

Panel title: `HTTP Request Rate`

This panel displays the rate of HTTP requests received by the application.

### Panel 3: Process Memory Usage

PromQL query:

```promql
process_resident_memory_bytes
```

Visualization: **Time series**

Panel title: `Process Memory Usage`

Unit: `Bytes`

This panel displays the resident memory used by the Node.js process.

### Panel 4: Node.js Heap Memory

PromQL query:

```promql
nodejs_heap_size_used_bytes
```

Visualization: **Time series**

Panel title: `Node.js Heap Memory`

Unit: `Bytes`

This panel displays the amount of Node.js heap memory currently in use.

## Generate Application Traffic

1. Open the Student Task Manager application.
2. Refresh the page several times.
3. Perform application operations to generate HTTP requests.
4. Return to the Grafana dashboard.
5. Observe changes in the HTTP request rate and memory panels.

## Expected Outcome

- Grafana is deployed and accessible.
- Prometheus is configured successfully as a data source.
- A dashboard named **Student Task Manager Monitoring Dashboard** is created.
- Application availability is displayed.
- HTTP request rate and memory usage are visualized.
- Node.js heap memory metrics are displayed.
- Dashboard panels update as new metrics are collected and application traffic changes.

## Screenshots

Include screenshots of:

- Grafana pod and Service running in Kubernetes.
- Grafana connected successfully to Prometheus.
- The Student Task Manager Monitoring Dashboard.
- Application Status panel.
- HTTP Request Rate panel.
- Process Memory Usage panel.
- Node.js Heap Memory panel.
- Dashboard changes after generating application traffic.


