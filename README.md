DevSecOps : Jenkins CI/CD Pipeline for Deploying the 2048 Game on Docker and Kubernetes with Full Observability & Metrics Archival using Amazon S3

I recently built a complete DevSecOps + Observability pipeline to deploy the 2048 React game using Jenkins CI/CD, Docker, Kubernetes, Prometheus, Grafana, with integrated security scanning and long-term metrics storage using Amazon S3 — turning it into a production-style environment..

📘 Project Overview:

📦 Source Code (GitHub Repository)

🔗 GitHub Repo: https://github.com/sajeebchandradas/2048-React-CICD.git


1️⃣ Infrastructure & Tooling Setup (AWS, Jenkins, Docker, SonarQube, Trivy)

* Provisioned Ubuntu AWS EC2 instances ☁️
* Installed & configured Jenkins, Docker, Trivy, SonarQube (Docker container) 🔧
* Added JDK 17, Node.js, and essential Jenkins plugins (Pipeline, Git, SonarQube Scanner, OWASP DC, Docker, Kubernetes) ⚙️
* Integrated Jenkins with **GitHub** and **Docker Hub** 🔗

---

2️⃣ Secure CI/CD Pipeline (Jenkins Declarative Pipeline) 🔐

* Automated stages:

  * Clean workspace
  * Git checkout
  * SonarQube SAST + Quality Gate
  * OWASP Dependency Check (SCA)
  * Trivy FS scan+ Trivy Image scan 🛡️
  * React build via Node.js dependencies


3️⃣ Containerization & Image Management (Docker) 🐳**

* Containerized the 2048 React App
* Built, tagged & pushed images to Docker Hub
* Performed automated image vulnerability scans via Trivy


4️⃣ Kubernetes Cluster Setup & Deployment (kubeadm, Calico CNI) ☸️

* Created multi-node Kubernetes cluster (master + worker)
* Installed kubectl, configured Calico CNI for networking 🐈‍⬛
* Joined worker nodes to the cluster
* Jenkins deployed manifests using kubeconfig credentials (`kubectl apply`)
* Exposed the game using a NodePort service 🌐


5️⃣ Observability & Monitoring Stack (Prometheus + Grafana) 📊

* Deployed:

  * kube-state-metrics (K8s objects)
  * Node Exporter (node-level metrics)
* Set up Prometheus for metrics scraping & alerting
* Built Grafana dashboards for:

  * Pod & deployment health
  * Node CPU/RAM
  * Cluster-wide resource utilization
  * App & container metrics


6️⃣ Long-Term Metrics Storage (Prometheus ➜ Amazon S3) 🗄️

* Configured Prometheus to export and store metrics in Amazon S3
* Enabled:

  * Long-term retention
  * Backup
  * External analytics
  * Historical performance trends 📈


🔧 Technologies Used

Jenkins, GitHub, SonarQube, OWASP Dependency Check, Trivy, Docker, Docker Hub, Kubernetes, kubeadm, kubectl, Calico CNI, kube-state-metrics, Node Exporter, Prometheus, Grafana, React, Node.js, JDK 17, AWS EC2, Amazon S3, Linux/Ubuntu.


