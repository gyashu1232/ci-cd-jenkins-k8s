# CI/CD Pipeline using Jenkins, Docker, and Kubernetes (Kind)

This project demonstrates a complete DevOps pipeline that builds, tests, and deploys a simple Flask-based web application using Jenkins, Docker, and Kubernetes (Kind).

---

## 📌 Project Overview

- 🐳 Docker is used to containerize a simple Python Flask application.
- 🔧 Jenkins automates the build and deployment process via a Jenkins pipeline.
- ☸️ Kubernetes (Kind) is used to deploy and manage the containerized application.
- 🧪 GitHub is used as a source code repository with collaborative branching and PR flow between two accounts.

---

## 📁 Project Structure

ci-cd-jenkins-k8s/
├── app/
│ ├── app.py # Simple Flask app
│ ├── requirements.txt # Python dependencies
│ └── Dockerfile # Image build file
├── k8s/
│ ├── deployment.yaml # Kubernetes Deployment
│ └── service.yaml # Kubernetes Service
├── Jenkinsfile # Jenkins pipeline definition
└── README.md # Project documentation

yaml
Copy code

---

## 🚀 Tech Stack

| Tool        | Purpose                                |
|-------------|----------------------------------------|
| Jenkins     | CI/CD Pipeline Orchestration           |
| Docker      | Containerization of Application        |
| Kubernetes  | Deployment and Scaling (via Kind)      |
| GitHub      | Source Control and Collaboration       |
| Flask       | Lightweight Python Web Framework       |

---

## 🧱 Step-by-Step Setup

### 1️⃣ Prerequisites

- Docker installed
- Kind (Kubernetes-in-Docker) cluster running
- `kubectl` configured for Kind
- Jenkins installed (can be Docker-based)
- GitHub accounts (owner and contributor)

### 2️⃣ Run Kind Cluster

```bash
kind create cluster --name devops-cluster
3️⃣ Build Docker Image
bash
Copy code
cd app/
docker build -t flask-cicd-app .
4️⃣ Deploy to Kubernetes
bash
Copy code
kubectl apply -f k8s/deployment.yaml
kubectl apply -f k8s/service.yaml
5️⃣ Access the App
Find NodePort and open in browser:

bash
Copy code
kubectl get service flask-service
🔄 Jenkins Pipeline Setup
Open Jenkins → New Item → Pipeline

Add GitHub repo in pipeline configuration

Use Jenkinsfile from the repo

Run the pipeline to:

Clone repo

Build Docker image

Deploy to Kubernetes

🔁 GitHub Collaboration Workflow
🔵 main-project-account: Project Owner

🟢 learning-account: Contributor

Fork or clone the repo

Create feature branches

Submit Pull Requests (PRs) to the main repo

📸 Screenshots
< Add Jenkins Pipeline, Kubernetes Pods, and App Output screenshots here >

✍️ Author
Owner GitHub: @your-owner-username

Contributor GitHub: @your-contributor-username

📃 License
This project is licensed under the MIT License - see the LICENSE file for details.
