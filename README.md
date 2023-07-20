# Project 6 Observerbility

Github public repo url: https://github.com/Veronaz/Project_6_Verona

Dockerhub public repo url: https://hub.docker.com/repository/docker/veronaz/project_5_verona

Note: Dockerhub image created from edited docker-react app; Pub repo link: https://github.com/StephenGrider/docker-react)

## Prerequisite

### Step 1 
Install docker cmd

### Step 2
Install kubectl cmd

### Step 3

download this repo and go within the folder
`git clone https://github.com/Veronaz/project_5_verona.git`

### Step 4
run kubectl cli 
1. create namespace
 `kubectl create ns verona`

2. apply deployment and service
   
 `kubectl apply -f deployment.yaml`

 `kubectl apply -f service.yaml`
 
Docker image references 

 *(replace the depoyment image reference to 'veronaz/project_5_verona:latest' if necessary)

ARM64:

 `Docker run -p 8080:80 veronaz/project_5_verona:latest`

x86_64:

 `Docker run -p 8080:80 veronaz/project_5_verona:amdlatest`

### Step 5
1. install fluentd

 `kubectl apply -f fluentd-config-map.yaml`

 `kubectl apply -f fluentd-dapr-with-rbac.yaml`

2. install promotheus and grafana

 `helm repo add prometheus-community https://prometheus-community.github.io/helm-charts`

`kubectl create ns monitoring`

`helm install monitoring prometheus-community/kube-prometheus-stack --namespace=monitoring`

`helm upgrade monitoring prometheus-community/kube-prometheus-stack --namespace=monitoring --values values.yaml`

3. Install k9s (optional for easily get pod/service names)

 `kubectl install k9s`
 `k9s`

4. Portforward
 
 Prometheus
 `kubectl port-forward -n monitoring <prometheus pod name> 9090:9090`
 
 Grafana
 `kubectl port-forward service/<monitoring-grafana> 3000:80 -n monitoring`

### Step 6

1. login prometheus 'https://localhost:9090'
   
2. login Grafana
   Go to 'https://localhost:3000'

   Username: admin

   Password: prom-operator

   (instruction: go into k9s grafana pod and use `base64 -d` decrypt the credentials in the file)
   
4. go to dashboards in Grafana

## Diagram

https://app.diagrams.net/#HVeronaz%2FProject_6_Verona%2Fmain%2Fproject_5_verona.drawio

![project_6_verona drawio](https://github.com/Veronaz/Project_6_Verona/assets/115947471/b2c953de-e8fc-4f91-9f27-9f18fd10f605)
