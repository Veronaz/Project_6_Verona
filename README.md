# Project 5 Kubernetes

Github public repo url: https://github.com/Veronaz/project_5_verona

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

## Diagram
https://github.com/Veronaz/project_5_verona/blob/main/project_5_verona.drawio


![project_5_verona drawio](https://github.com/Veronaz/project_5_verona/assets/115947471/73360353-6d7a-49f2-96de-5401be0ab122)

## Project requirement

### Project 5 - Kubernetes
Due date: July 16, 2023

Architecture

DevOps - Project 5 - Kubernetes.png

In this project, students will work in a team to deploy a web app onto a cloud production Kubernetes cluster that can be consumed by user on the public internet. Because this is deployed in a Kubernetes environment the orchestration of the app containers is done using the Kubernetes tech stack. Though there are many flavors of managed Kubernetes services, for this specific project students will leverage AWS's managed Kubernetes service AWS Elastic Kubernetes Service (EKS) for their cloud production Kubernetes cluster.


Requirements

1. Create a web app or leverage a web app that is already publicly available - for e.g. on GitHub.

2. Dockerize the app.

- Create Dockerfile with instructions to create the respective Docker image for this app.

- Create a DockerHub account - if you don’t already have one.

- Build the Docker images in both x86_64 and arm64 formats - e.g. use Docker Buildx tool - and push the Docker images to your DockerHub registry

3. Deploy and orchestrate the app containers with the AWS managed Kubernetes service AWS EKS.

  For this project when creating the Kubernetes infrastructure using AWS EKS you can use either options:

- The classic EC2 nodes.
- Serverless with AWS Fargate.

  
  Create the necessary Kubernetes manifest files for the deployment of your app in a Kubernetes cluster.

4. Launch and run your app containers in the configured AWS EKS Kubernetes cluster(s) and ensure your app is accessible by users from the public internet.

- Your app and relevant ports should be exposed.

- The app should have a valid IP address or DNS endpoint where users can connect to from their browser.


5. Documentation

  Create a README.md in your GitHub repo.

  In the README.md

- Include an architectural diagram of your app and Kubernetes environment setup in the README.md

- Include instructions on how users can access your app.

- Include instructions on how users can use your provided Dockerfiles and Kubernetes manifest files to generate the relevant container images and launch the containers in their own Kubernetes cluster and environment.


Submission Instructions

1. In the README.md of your GitHub repo include the names of members in your group.

2. Download a Zip file of your completed GitHub repo.

3. Click on Hand In tab in the learning portal project page.

4. Click on Upload Assignment and upload the zip file.


After you have submitted your assignment:

Make your web app available on the public internet - e.g. turn on your AWS EKS that is hosting the containerized web app - and notify Nhat with the relevant app URL.

Nhat will then test accessing your web app from the public internet.

