# 🚀 End-to-End DevOps CI/CD Platform on AWS

**Terraform | Jenkins | Docker | Node.js | AWS EC2**

---

## 📌 Project Overview

This project demonstrates a **production-ready DevOps pipeline** that automates infrastructure provisioning, application build, containerization, and deployment on AWS.

It showcases how to integrate **Infrastructure as Code (Terraform)** with **CI/CD (Jenkins)** and **containerization (Docker)** to deliver a scalable and automated deployment workflow.

---

## 🏗️ Architecture

```
GitHub → Jenkins → Docker Build → Docker Hub → EC2 Deployment → User Access
```

### Flow Explanation:

1. Developer pushes code to GitHub
2. Jenkins pipeline is triggered
3. Docker image is built and tagged
4. Image is pushed to Docker Hub
5. Jenkins deploys container on AWS EC2
6. Application is accessible via browser

---

## ⚙️ Tech Stack

| Category         | Tools             |
| ---------------- | ----------------- |
| Cloud            | AWS EC2           |
| IaC              | Terraform         |
| CI/CD            | Jenkins           |
| Containerization | Docker            |
| Backend          | Node.js (Express) |
| Version Control  | Git & GitHub      |

---

## 📁 Project Structure

```
jenkins-devops-platform/
│
├── app/
│   ├── index.js
│   ├── package.json
│   ├── Dockerfile
│   └── public/
│       └── index.html
│
├── jenkins/
│   └── Jenkinsfile
│
├── terraform/
│   ├── main.tf
│   ├── variables.tf
│   ├── outputs.tf
│   └── userdata.sh
│
├── scripts/
│   └── deploy.sh
│
├── docs/
│   ├── architecture.md
│   └── screenshots/
│
├── .gitignore
└── README.md
```

---

## 🚀 Features

* ✅ Automated infrastructure provisioning using Terraform
* ✅ CI/CD pipeline using Jenkins
* ✅ Docker image build and deployment
* ✅ Health check endpoint (`/health`)
* ✅ Zero manual deployment steps
* ✅ Secure configuration (IMDSv2, restricted SSH)
* ✅ Production-ready Node.js application

---

## 🔄 CI/CD Pipeline Stages

1. **Checkout Code** – Pulls code from GitHub
2. **Build** – Builds Docker image
3. **Test** – Runs container and validates API
4. **Push** – Pushes image to Docker Hub
5. **Deploy** – Deploys container on EC2
6. **Health Check** – Validates application availability

---

## 🖥️ Setup & Deployment

### 🔹 1. Clone Repository

```bash
git clone https://github.com/prathitagarje/jenkins-ec2-deployment.git
cd jenkins-ec2-deployment
```

---

### 🔹 2. Provision Infrastructure (Terraform)

```bash
cd terraform
terraform init
terraform apply
```

👉 This will:

* Launch EC2 instance
* Install Jenkins
* Configure Docker

---

### 🔹 3. Access Jenkins

```text
http://<EC2-PUBLIC-IP>:8080
```

Retrieve admin password:

```bash
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```

---

### 🔹 4. Configure Jenkins

* Install suggested plugins
* Add Docker Hub credentials
* Create pipeline job
* Connect GitHub repository

---

### 🔹 5. Run Pipeline

* Trigger build manually or via GitHub webhook
* Monitor pipeline stages

---

### 🔹 6. Access Application

```text
http://<EC2-PUBLIC-IP>:3000
```

---

## 🐳 Docker Commands (Manual Testing)

```bash
docker build -t basic-webapp .
docker run -p 3000:3000 basic-webapp
```

---

## 🔍 Health Check

```bash
curl http://localhost:3000/health
```

Response:

```json
{
  "status": "UP"
}
```

---

## 🔐 Security Best Practices

* IMDSv2 enabled for EC2
* SSH access restricted via CIDR
* Sensitive files excluded using `.gitignore`
* Docker container runs with restart policy

---

## 📸 Screenshots (Add here)

* Jenkins pipeline success
* Terraform apply output
* Application running in browser

---

## 📈 Future Enhancements

* 🔹 Deploy using Kubernetes (EKS)
* 🔹 Integrate SonarQube for code quality
* 🔹 Push Docker images to AWS ECR
* 🔹 Add Load Balancer with HTTPS
* 🔹 Implement Blue-Green deployment

---

## 🎯 Key Learnings

* End-to-end CI/CD pipeline design
* Infrastructure automation using Terraform
* Container lifecycle management
* Jenkins pipeline creation and optimization
* Production-grade deployment practices

---

## 👨‍💻 Author

**Prathita Garje**

---

## ⭐ If you found this project useful

Give it a ⭐ on GitHub and feel free to fork!
