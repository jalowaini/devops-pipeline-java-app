# Java CI/CD Pipeline – Spring Boot + Jenkins + AWS EKS

## 📌 Overview
A production-grade CI/CD pipeline that builds, packages, Dockerizes, and deploys a Java Spring Boot application to AWS EKS using Jenkins. The entire workflow is automated using a Jenkins Pipeline.

---

## 🧰 Tech Stack

| Tool/Service | Purpose |
|--------------|---------|
| Java 17      | Backend Application |
| Maven        | Build Tool |
| Docker       | Containerization |
| Jenkins      | CI/CD Pipeline |
| Amazon ECR   | Docker Image Registry |
| Amazon EKS   | Kubernetes Cluster |
| kubectl      | Cluster Management |
| AWS CLI      | AWS Operations |

---

## 🧱 Architecture

```text
[ GitHub Repo ]
      ↓
[ Jenkins (Docker on EC2) ]
      ↓
[ Maven Build → .jar ]
      ↓
[ Docker Build → Image ]
      ↓
[ Push to Amazon ECR ]
      ↓
[ Deploy to Amazon EKS ]
      ↓
[ Access via LoadBalancer Service ]
🛠️ Jenkins Pipeline Stages

Stage	Description
Checkout	Clones the GitHub repo
Build	Builds the .jar using Maven
Docker Build & Push	Builds Docker image and pushes to ECR
Deploy to EKS	Applies deployment and service manifests
Post-deploy Test	Verifies app is reachable
✅ Results
CI/CD fully automated

Application is running on EKS with external access

Future-ready for HTTPS, Monitoring, Helm, ArgoCD

📌 Author
Built with ❤️ by @jalowaini
