<div align="center">

# 🐳 AWS Portfolio — Docker Deployment

### Containerizing a static website using Docker & Nginx

[![Docker](https://img.shields.io/badge/Docker-Container-2496ED?style=flat&logo=docker&logoColor=white)](https://www.docker.com/)
[![Nginx](https://img.shields.io/badge/Nginx-Alpine-009639?style=flat&logo=nginx&logoColor=white)](https://nginx.org/)
[![AWS](https://img.shields.io/badge/AWS-S3-FF9900?style=flat&logo=amazon-aws&logoColor=white)](https://aws.amazon.com/s3/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

</div>

---

## 📌 Overview

This project containerizes my personal AWS cloud portfolio website using **Docker** and a lightweight **Nginx (Alpine)** web server — solving the classic *"it works on my machine"* problem by packaging the app and its environment into a single, portable image.

The same website is already live on **AWS S3** as a static site. This project demonstrates the ability to deploy the *exact same application* in a containerized form, a core skill for modern cloud and DevOps workflows.

---

## 🧠 Why This Matters

| Without Docker | With Docker |
|---|---|
| Manual server setup, install web server | One command builds the entire environment |
| "Works on my machine" issues | Identical behavior anywhere — laptop, server, cloud |
| Hard to scale or replicate | Image can spin up N identical containers instantly |

---

## 🛠️ Tech Stack

- **Containerization:** Docker
- **Base Image:** `nginx:alpine` (lightweight Linux + web server)
- **Frontend:** HTML, CSS
- **OS Environment:** WSL2 (Ubuntu) on Windows

---

## ⚙️ How It Works
Dockerfile  →  docker build  →  Image  →  docker run  →  Running Container  →  localhost:8080

**Dockerfile breakdown:**

```dockerfile
FROM nginx:alpine
COPY index.html /usr/share/nginx/html/index.html
EXPOSE 80
```

| Instruction | Purpose |
|---|---|
| `FROM` | Uses a minimal Nginx web server as the base image |
| `COPY` | Copies the website file into Nginx's default serving directory |
| `EXPOSE` | Documents that the container listens on port 80 |

---

## ▶️ Usage

**1. Clone the repo**
```bash
git clone https://github.com/sayedabdulmuqsit/aws-portfolio-docker-deployment.git
cd aws-portfolio-docker-deployment
```

**2. Build the image**
```bash
docker build -t my-portfolio .
```

**3. Run the container**
```bash
docker run -d -p 8080:80 my-portfolio
```

**4. View it live**
http://localhost:8080

---

## 📂 Project Structure
aws-portfolio-docker-deployment/

├── Dockerfile

├── index.html

└── README.md
---

## 💡 Key Concepts Demonstrated

- Writing a Dockerfile from scratch
- Building Docker images (`docker build`)
- Running containers with port mapping (`docker run -p`)
- Understanding the Image vs Container distinction
- Container lifecycle management (`docker ps`, `docker stop`)

---

## 🔮 Future Improvements

- [ ] Push image to Docker Hub for public pulls
- [ ] Multi-stage build for further size optimization
- [ ] Deploy container to AWS ECS/EKS
- [ ] Integrate into a CI/CD pipeline (GitHub Actions)

---

## 👤 Author

**Abdul Muqsit Sayed**
CSE (AI/ML) Student | Cloud Computing Enthusiast
[GitHub](https://github.com/sayedabdulmuqsit) • [Portfolio](http://muqsit-portfolio-site.s3-website.eu-north-1.amazonaws.com)
