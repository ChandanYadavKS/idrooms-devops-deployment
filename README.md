# 🚀 IDRooms DevOps Deployment

This repository demonstrates the complete DevOps implementation for the **IDRooms application**, including CI/CD pipeline, Docker-based deployment, and production setup on AWS.

---

## 👨‍💻 My Role

As a **DevOps Engineer**, I was responsible for:

- Setting up AWS EC2 production server (Ubuntu)
- Installing and configuring Jenkins for CI/CD
- Automating frontend deployment using Jenkins pipeline
- Containerizing frontend and backend using Docker
- Deploying backend manually using Docker Compose
- Configuring Nginx as reverse proxy
- Mapping domains using DNS
- Managing production deployment and updates

---

## 🛠️ Tech Stack

- **Cloud:** AWS EC2
- **CI/CD:** Jenkins
- **Containerization:** Docker, Docker Compose
- **Web Server:** Nginx
- **Version Control:** GitHub
- **OS:** Ubuntu Linux

---

## 🏗️ Architecture

![Architecture](screenshots/architecture.png)

---

## ⚙️ Frontend Deployment (CI/CD)

Frontend deployment is automated using Jenkins.

### Flow
1. Code is pushed to GitHub
2. Jenkins pipeline is triggered
3. Docker image is built
4. Old container is stopped and removed
5. New container is deployed
6. Domain is mapped through DNS
7. Nginx routes traffic to the running container

---

## ⚙️ Backend Deployment

Backend is deployed manually using Docker Compose.

### Flow
1. Pull backend code from GitHub
2. Configure `.env` file
3. Add required key files
4. Build Docker image
5. Run backend using Docker Compose
6. Configure Nginx for API domain routing

---

## 🌐 Domain and Service Mapping

| Service | Domain | Container | Port |
|---|---|---|---|
| User Website | `idrooms.in` | `id-rooms` | `3002` |
| Backend API | `api.idrooms.in` | `idrooms-backend` | `internal` |
| Partner Admin | `idroomspartner.in` | `admin_idrooms` | `3003` |
| Super Admin | `llidsup.com` | `superadmin_idrooms` | `3004` |
| Staff Panel | `idsupport.in` | `idrooms-staff-frontend` | `3006` |
| Marketing Site | `mmidrs.com` | `idrooms-marketing-frontend` | `3005` |

---

## 🌐 Nginx & Domain Setup

- DNS A records are mapped to the EC2 public IP
- Nginx is configured as a reverse proxy for each domain
- Separate domain routing is maintained for frontend panels and backend API

---

## 📸 Screenshots

### Jenkins Pipeline
![Jenkins Pipeline](screenshots/jenkins-pipeline-success.png)

---

## 📁 Project Structure

```text
idrooms-devops-deployment/
│
├── frontend/
│   └── Dockerfile
│
├── backend/
│   └── Dockerfile
│
├── jenkins/
│   └── Jenkinsfile
│
├── nginx/
│   └── idrooms.conf
│
├── docs/
│
└── screenshots/
