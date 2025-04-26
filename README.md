Java CI/CD Pipeline – Spring Boot + Jenkins + AWS EKS

A production-grade CI/CD pipeline that builds, Dockerizes, and deploys a Java Spring Boot application on AWS using Jenkins, ECR, and EKS.

---

## Tech Stack

| Tool / Service | Purpose                        |
|----------------|--------------------------------|
| Java 17        | Backend Application            |
| Maven          | Build Tool                     |
| Docker         | Containerization               |
| Jenkins        | CI/CD Automation               |
| Amazon ECR     | Docker Image Registry          |
| Amazon EKS     | Kubernetes Cluster             |
| AWS CLI        | AWS Operations & Authentication|
| kubectl        | Kubernetes CLI Tool            |

---

## Architecture Overview

[ GitHub Repo ] ↓ [ Jenkins (Docker on EC2) ] ↓ [ Maven Build → .jar ] ↓ [ Docker Build → Image ] ↓ [ Push to Amazon ECR ] ↓ [ Deploy to Amazon EKS ] ↓ [ Access via LoadBalancer Service ]

---

## Jenkins Pipeline Stages

| Stage             | Description                                        |
|-------------------|----------------------------------------------------|
| Checkout        | Pulls source code from GitHub                      |
| Maven Build     | Compiles project and generates `.jar`              |
| Docker Build    | Builds Docker image from the `.jar`                |
| Push to ECR     | Pushes the Docker image to Amazon ECR             |
| Deploy to EKS   | Applies Kubernetes manifests (deployment/service) |
| Post-deploy Test| Verifies that the app is running and reachable     |

---

## Results

- CI/CD is fully automated via Jenkins  
- Docker Image stored in **Amazon ECR**  
- App is deployed to **Amazon EKS** with public access  
- Structure is production-ready and easily extensible  
 
---

## 👨‍💻 Author

Built with ❤️ by [@jalowaini](https://github.com/jalowaini)

