# Kubernetes One Shot — Projects & Learning Outcomes

**Video Reference:** [Kubernetes In One Shot | TrainWithShubham](https://youtu.be/W04brGNgxN4?si=MWZBPfTm62lBvcvN)  
**GitHub Repository:** [https://github.com/nachiketa11/kubernetes-devops-project](https://github.com/nachiketa11/kubernetes-devops-project)

---

## 📌 Executive Summary of Learnings

### 1. Core Architecture & Control Plane Components
* **Control Plane:** Understood the roles of `kube-apiserver` (central API gateway), `etcd` (key-value cluster state storage), `kube-scheduler` (assigning workload pods), and `kube-controller-manager` (reconciling desired state).
* **Worker Nodes:** Explored `kubelet` execution agent, `kube-proxy` networking layer, and container runtimes.

### 2. Workload Controllers & Stateful Storage
* **Pods & Deployments:** Implemented declarative updates, self-healing, rolling deployments, and scaling replicas using Deployment controllers.
* **Services & Networking:** Understood service abstraction types (`ClusterIP` for internal communication, `NodePort` for external access, and `LoadBalancer` for cloud integration).
* **Stateful Applications:** Configured persistent storage for databases (e.g., MongoDB) using `PersistentVolume` (PV) and `PersistentVolumeClaim` (PVC).

### 3. GitOps & Observability
* **GitOps with ArgoCD:** Automated continuous deployment pipelines by syncing cluster state directly with Git source repositories using ArgoCD Application manifests.
* **Monitoring Stack:** Deployed Prometheus and Grafana via Helm charts to track cluster-level metrics (CPU, Memory utilization, Pod restarts).

---

## 🛠️ Project Structure & Artifacts

1. `01-k8s-basics/`: Declarative Deployment and NodePort Service.
2. `02-three-tier-app/`: Persistent Storage allocation for Database tiers.
3. `03-helm-argocd/`: ArgoCD GitOps custom resource definitions.
4. `04-monitoring/`: Helm configuration values for Prometheus and Grafana setup.
