# 📝 Django To-Do App on Minikube (with Prometheus & Grafana Monitoring)

## 📌 Project Overview
This project demonstrates a **Django-based To-Do application** deployed on **Kubernetes (Minikube)** with **Prometheus & Grafana monitoring** integration.

It showcases:
- Containerization with Docker  
- Kubernetes Pods, Services & Deployments  
- Monitoring with Prometheus + Grafana  

---

## 📂 Project Structure
minikube-django-todo/
│── django-todo-app/
│── k8s-manifests/
│ ├── django-deployment.yaml
│ ├── django-service.yaml
│ ├── prometheus-deployment.yaml
│ ├── grafana-deployment.yaml
│ ├── monitoring-service.yaml
│
│── README.md

## ⚙️ Setup Instructions

### 1. Clone Repository
```bash
git clone https://github.com/<your-username>/minikube-django-todo.git
cd minikube-django-todo

### 2. Start Minikube

minikube start --memory=4096 --cpus=2
kubectl get nodes

### 3. Build Docker Image

eval $(minikube docker-env)
docker build -t django-todo-app ./django-todo-app

### 4. Deploy Django To-Do App

kubectl apply -f k8s-manifests/django-deployment.yaml
kubectl apply -f k8s-manifests/django-service.yaml

### 5. Access Django Application

minikube service django-service

### 6. Deploy Monitoring (Prometheus + Grafana)

kubectl apply -f k8s-manifests/prometheus-deployment.yaml
kubectl apply -f k8s-manifests/grafana-deployment.yaml
kubectl apply -f k8s-manifests/monitoring-service.yaml

### 7. Access Monitoring Tools

    Prometheus

minikube service prometheus-service

    Grafana

minikube service grafana-service

Default Grafana credentials:

Username: admin
Password: admin




<img width="1916" height="1075" alt="Screenshot from 2025-08-26 02-23-01" src="https://github.com/user-attachments/assets/2770b3f2-0a6c-49b6-b720-2ea57ff3fe7a" />
<img width="1916" height="1075" alt="Screenshot from 2025-08-26 02-22-38" src="https://github.com/user-attachments/assets/2e34d0d5-e725-4a7c-a43f-23c2a85f70fd" />
<img width="1916" height="1075" alt="Screenshot from 2025-08-26 02-26-22" src="https://github.com/user-attachments/assets/b8978501-900f-4ae7-bc54-e08bb51e8b2b" />

