# 🚀 CI/CD Pipeline with Docker Swarm & Nginx

## 📌 Project Overview

This project demonstrates a complete **CI/CD pipeline** using Jenkins, Docker, Docker Swarm, and Nginx.

The pipeline automatically builds, pushes, and deploys multiple microservices when code is pushed to GitHub.

---

## 🏗️ Architecture


GitHub → Webhook → Jenkins → Docker Build → Docker Hub → Docker Swarm → Nginx

<img width="1536" height="1024" alt="docker" src="https://github.com/user-attachments/assets/cbfe6f87-82eb-497b-9306-af4c3e296280" />




---

## ⚙️ Tech Stack

* **GitHub** – Source code repository
* **Jenkins** – CI/CD automation
* **Docker** – Containerization
* **Docker Swarm** – Container orchestration
* **Docker Hub** – Image registry
* **Nginx** – Reverse proxy & load balancer
* **AWS EC2** – Hosting infrastructure

---

## 📦 Services

The application consists of multiple microservices:

* 🏦 Internet Banking
* 📱 Mobile Banking
* 🛡️ Insurance
* 💰 Loan

Each service runs in its own container and is managed by Docker Swarm.

---

## 🔄 CI/CD Workflow

1. Developer pushes code to GitHub
2. GitHub triggers Jenkins via webhook
3. Jenkins pipeline executes:

   * Checkout code
   * Build Docker image
   * Tag image
   * Push image to Docker Hub
   * Deploy stack using Docker Swarm
4. Nginx routes traffic to respective services

---



## 🐳 Docker Swarm Deployment

Initialize swarm:

```
docker swarm init
```

Deploy stack:

```
docker stack deploy -c docker-compose.yml bank
```

Check services:

```
docker stack ps bank
```

---

## 🔧 Jenkins Pipeline

The pipeline includes stages:

* Checkout code
* Build Docker image
* Tag image
* Push to Docker Hub
* Deploy using Docker Swarm

---

## 🔗 Webhook Configuration

GitHub webhook is configured to trigger Jenkins automatically on every push:

```
http://<EC2-PUBLIC-IP>:8080/github-webhook/
```

---

## 📁 Project Structure

```
.
├── docker-compose.yml
├── nginx.conf
├── Dockerfile
├── index.html
└── Jenkinsfile
```

---

## 🎯 Key Features

* Automated CI/CD pipeline
* Multi-container deployment
* Load balancing with Nginx
* Docker Swarm orchestration
* Webhook-based automation

---

## 💡 Future Enhancements

* Add HTTPS (SSL) support
* Implement monitoring (Prometheus + Grafana)
* Add rollback strategy
* Use Jenkins credentials for security

---

## 👩‍💻 Author

**Riya Kumari**

---

## ⭐ Conclusion

This project demonstrates a real-world DevOps workflow by integrating CI/CD, containerization, orchestration, and reverse proxy.

---
