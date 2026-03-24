# Welcome to the DevSecOps Pipeline Project

## 🍁 Introduction

This project demonstrates the use of modern **DevSecOps** methodologies for
scalable, secure, and automated microservice deployment on **Kubernetes (EKS)**,
using a GitOps-driven workflow with end-to-end observability.

[![MIT License](https://img.shields.io/badge/License-MIT-green.svg)](https://choosealicense.com/licenses/mit/)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Profile-blue)](https://www.linkedin.com/in/pratik-k36/)
[![GitHub](https://img.shields.io/badge/GitHub-Pratikkumare-black)](https://github.com/Pratikkumare)


## 🛠️ Tools & Services Used

| **Category**       | **Tools**                                                                                                                                                                                                 |
|---------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Version Control** | ![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat-square&logo=github&logoColor=white)                                                                                                       |
| **CI/CD**           | ![Jenkins](https://img.shields.io/badge/Jenkins-D24939?style=flat-square&logo=jenkins&logoColor=white)                                                                                                    |
| **Code Quality**    | ![SonarQube](https://img.shields.io/badge/SonarQube-4E9BCD?style=flat-square&logo=sonarqube&logoColor=white)                                                                                              |
| **Containerization**| ![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)                                                                                                       |
| **Orchestration**   | ![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=flat-square&logo=kubernetes&logoColor=white)                                                                                          |
| **Monitoring**      | ![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=flat-square&logo=prometheus&logoColor=white) ![Grafana](https://img.shields.io/badge/Grafana-F46800?style=flat-square&logo=grafana&logoColor=white) |
| **Security**        | ![OWASP](https://img.shields.io/badge/OWASP-000000?style=flat-square&logo=owasp&logoColor=white) ![Trivy](https://img.shields.io/badge/Trivy-00979D?style=flat-square&logo=trivy&logoColor=white)         |
| **IAC**             | ![Terraform](https://img.shields.io/badge/Terraform-623CE4?style=flat-square&logo=terraform&logoColor=white)



## 🍁 Setup

- Follow the step-by-step instructions in `setup-instruction.txt`
- [Setup Instructions](./setup-instruction.txt)

## 🍁 Project Phases

### Phase 1: Infrastructure Provisioning

- Provisioned and scaled AWS EKS infrastructure using modular Terraform configurations.
- Managed the full lifecycle of containerized environments from cluster creation to teardown.
```bash
terraform init && terraform apply -auto-approve
```

### Phase 2: CI/CD Pipeline & GitOps

- Built automated pipelines using GitHub Actions for continuous integration and image builds.
- Implemented GitOps workflow using Argo CD for seamless microservice deployments with zero manual intervention. 
```bash
argocd app sync devops-app
```

### Phase 3: Networking & Traffic Management

- Configured Route53, Ingress controllers, and Kubernetes networking to manage secure traffic routing and service discovery. 
```bash
kubectl apply -f kubernetes/ingress.yaml
```

### Phase 4: Security Integration

- Integrated Trivy for container image vulnerability scanning at every pipeline stage.
- Enforced code quality standards using SonarQube across all microservices.
```bash
trivy image --exit-code 1 --severity HIGH,CRITICAL your-image:tag
```

### Phase 5: Monitoring & Observability

- Deployed Prometheus and Grafana for cluster-level and application-level metrics monitoring.
- Enabled proactive alerting to detect and resolve issues before end-user impact. 
```bash
kubectl port-forward svc/grafana 3000:3000 -n monitoring
```

## 🍁 Conclusion

* This project validates how modern DevOps and DevSecOps practices can be combined
to deliver microservices reliably on Kubernetes.
* By integrating CI/CD, GitOps, security scanning, networking, and observability,
the deployment process becomes automated, secure, and production-ready.
The implementation serves as a practical blueprint for real-world cloud-native deployments. 🚀

### Thanks for checking out this project! Happy automating! 🚀