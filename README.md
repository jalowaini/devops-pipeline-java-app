🚀 Java CI/CD Pipeline with Jenkins, Docker, and AWS EKS

A complete production-grade CI/CD pipeline that builds, containerizes, and deploys a Spring Boot application to Kubernetes (EKS) using Jenkins.

🧱 Architecture Flow

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
[ Access via LoadBalancer ]
🔄 Jenkins Pipeline Stages


Stage	Description
✅ Checkout	Pulls source code from GitHub
✅ Maven Build	Compiles code and generates .jar file
✅ Docker Build/Push	Builds image and pushes to Amazon ECR
✅ Deploy to EKS	Applies Kubernetes manifests (deployment + service)
✅ Post-deploy Test	Verifies application is accessible externally
✅ Results

CI/CD is fully automated with Jenkins

Docker image is stored in Amazon ECR

Application is deployed on AWS EKS and accessible via LoadBalancer

Production-ready design: clean, scalable, and modular

🔮 What's Next?

This pipeline can be enhanced further with:

🔐 HTTPS via Ingress + Cert-Manager

📈 Monitoring with Prometheus + Grafana

📦 Helm Charts or ArgoCD for GitOps

🧪 Automated post-deploy testing

👨‍💻 Author

Built with ❤️ by [@jalowaini](https://github.com/jalowaini)
