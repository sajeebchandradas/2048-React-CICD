📘 Project Overview:

📦 Source Code (GitHub Repository)
🔗 GitHub Repo: https://github.com/sajeebchandradas/2048-React-CICD.git

Designed and implemented an end-to-end DevSecOps + Observability pipeline to deploy the open-source 2048 React game on Docker and Kubernetes using Jenkins CI/CD, with integrated security scanning and long-term metrics storage.
1️⃣  Infrastructure & Tooling Setup (AWS EC2, Jenkins, Docker, SonarQube, Trivy)
o	Provisioned Ubuntu AWS EC2 instances and installed Jenkins, Docker, Trivy, and SonarQube (Docker container).
o	Configured JDK 17, Node.js, and necessary Jenkins plugins (Pipeline, Git, SonarQube Scanner, OWASP Dependency Check, Docker, Kubernetes, etc.).
o	Connected Jenkins with GitHub for source code and Docker Hub as the container registry.
2️⃣  Secure CI/CD Pipeline (Jenkins Declarative Pipeline) 🛡️
o	Built a multi-stage Jenkins declarative pipeline to automatically:
	Clean workspace and checkout code from GitHub.
	Run SonarQube SAST / code quality analysis with quality gates.
	Run OWASP Dependency Check (SCA) for library vulnerabilities.
	Execute Trivy filesystem scans and Trivy Docker image scans.
	Install Node.js dependencies and run build steps for the React app.
3️⃣  Containerization & Image Management (Docker, Docker Hub, Trivy) 🐳
o	Containerized the 2048 React application using Docker.
o	Built, tagged, and pushed images to Docker Hub from the Jenkins pipeline.
o	Scanned Docker images using Trivy and stored scan reports as pipeline artifacts.
4️⃣  Kubernetes Cluster Setup & Deployment (kubeadm, kubectl, Calico CNI) ☸️
o	Created a Kubernetes cluster with kubeadm on separate master and worker Ubuntu nodes.
o	Installed kubectl, configured Calico CNI, and joined worker nodes to the cluster.
o	Integrated Jenkins with Kubernetes using kubeconfig credentials and deployed app manifests (deployment.yaml, service) via kubectl apply.
o	Exposed the game using a NodePort service and validated access via browser.
5️⃣  Observability & Cluster Monitoring (kube-state-metrics, Node Exporter, Prometheus, Grafana) 📊
o	Deployed kube-state-metrics for Kubernetes object metrics and Node Exporter for node-level system metrics.
o	Set up Prometheus to scrape metrics from Kubernetes, nodes, and exporters.
o	Built Grafana dashboards to visualize: pod/Deployment health, node CPU/RAM, cluster resource usage, and application behavior.
6️⃣  Long-Term Metrics Storage & Analytics (Prometheus → Amazon S3) 🗄️
o	Configured Prometheus to store/export metrics data to an Amazon S3 bucket for long-term retention, backup, and external analytics.
o	Enabled the ability to perform historical performance analysis and capacity planning using archived metrics.
🔧  Technologies used: Jenkins, GitHub, SonarQube, OWASP Dependency Check, Trivy, Docker, Docker Hub, Kubernetes, kubeadm, kubectl, Flannel CNI, kube-state-metrics, Node Exporter, Prometheus, Grafana, React, Node.js, JDK 17, AWS EC2, Amazon S3, Linux/Ubuntu.

🎯 Key Learnings
•	Building a secure, automated CI/CD pipeline using Jenkins Declarative Pipeline
•	Implementing SAST, SCA, and container vulnerability scans using SonarQube, OWASP DC, and Trivy
•	Containerizing applications with Docker and pushing images to Docker Hub
•	Setting up a production-style Kubernetes cluster using kubeadm with Calico CNI
•	Automating Kubernetes deployments via Jenkins using kubeconfig integration
•	Implementing full Kubernetes and node-level observability using:
o	kube-state-metrics
o	Node Exporter
o	Prometheus
o	Grafana
•	Creating real-time dashboards for cluster health, pod behavior, resource utilization, and performance trends
•	Storing Prometheus metrics in Amazon S3 for long-term retention, backup, and advanced analytics
•	Strengthening practical skills across DevOps, DevSecOps, Kubernetes, Monitoring, and Cloud Storage
•	Gaining hands-on experience in building a complete end-to-end delivery + security + monitoring architecture
