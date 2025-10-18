# 🚀 First-k8s — Node.js Web Server on Kubernetes

This project demonstrates how to containerize a simple Node.js web application and deploy it on Kubernetes.
Each running Pod exposes a unique hostname to show load balancing in action.

## 📂 Project Structure

├── index.mjs              # Express web server
├── Dockerfile             # Docker build configuration
├── deployment.yaml        # Kubernetes Deployment manifest
├── service.yaml           # Kubernetes Service manifest
└── package.json           # Node.js dependencies

## 🧩 Application Overview
The web server is built using Express.js and listens on port 3000.
Each response returns the hostname of the Pod handling the request:

Hello World, I am Pod <pod-name>


This helps visualize load balancing between Pods in the Kubernetes cluster.

## 🐳 Docker Setup

Build the Docker Image
docker build -t nourhankhalidd/first-k8s .

Run the Container Locally
docker run -p 3000:3000 nourhankhalidd/first-k8s
Then open http://localhost:3000

## ☸️ Kubernetes Deployment
1. Apply the Deployment
kubectl apply -f deployment.yaml

2. Apply the Service
kubectl apply -f service.yaml

3. Verify Resources
kubectl get all

## 🌐 Accessing the Application

Find the NodePort assigned to your service:
kubectl get svc

Access the app in your browser at:
http://localhost:<NodePort>

### Each refresh should display a different Pod hostname — confirming load balancing.

## 🧠 Key Concepts

Express.js – lightweight web framework for Node.js
Docker – containerization of the app
Kubernetes Deployment – manages replicas and updates
Kubernetes Service (NodePort) – exposes the app to external traffic

## 🛠️ Tools Used
Node.js 
Docker
Kubernetes (via Docker Desktop)
kubectl CLI

## 👩‍💻 Author

Nourhan Khalid
GitHub: @nourhankhalidd
