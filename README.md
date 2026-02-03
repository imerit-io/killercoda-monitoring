# Monitoring Troubleshooting Test

Welcome! You have access to a Kubernetes cluster.

Your task is to fix the **broken Prometheus + Grafana setup** so that:

1. Prometheus successfully scrapes metrics from `sample-app`.
2. Targets appear as `UP` in Prometheus.
3. Grafana dashboards display metrics correctly.



### Instructions

1. Install all Yamls
   After requisite namespace creation
   kubectl apply -f https://raw.githubusercontent.com/prometheus-operator/prometheus-operator/v0.73.0/example/prometheus-operator-crd/monitoring.coreos.com_servicemonitors.yaml
   kubectl apply -f monitoring/ 
   kubectl apply -f app/ 

2. Killercoda instance needs port forwarding on all IP not just localhost ie, 0.0.0.0 must be explicitly mentioned as address parameter of port-forward. Required to visualize Grafana dashboard
   Click on hamburger menu at the top right and Traffic /Ports to open the grafana dashboard

3. Explore the monitoring namespace and resources:
   ```bash
   kubectl get all -n monitoring
   kubectl logs -n monitoring <prometheus-pod>

Inspect the app metrics:

 kubectl get svc -n app


Identify issues in the YAML files.


Apply your fixes and validate targets.


Once fixed, write a short explanation of:


What was broken


How you fixed it


Why your fix works


Notes
Do not follow step-by-step tutorials — this is a troubleshooting exercise.


You may edit any YAML files.


Show screenshots or kubectl get pods -n monitoring output as proof.
