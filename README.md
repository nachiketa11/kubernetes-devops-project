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


## Quickstart and validation checklist

### Prerequisites

- A working Kubernetes cluster (for example, Docker Desktop Kubernetes or Minikube).
- `kubectl` configured to target that cluster.
- Helm installed for the Helm-based examples.
- Argo CD installed only when working through the GitOps section.

Check the active cluster before applying manifests:

```bash
kubectl config current-context
kubectl cluster-info
kubectl get nodes
```

### Apply and inspect a basic workload

From the `01-k8s-basics/` directory, inspect the YAML files first, then apply the intended manifest files:

```bash
kubectl apply -f <manifest-file>.yaml
kubectl get deployments,pods,services
kubectl describe deployment <deployment-name>
kubectl rollout status deployment/<deployment-name>
```

Replace the placeholder names with the actual resources defined in the manifests. Avoid applying every YAML file recursively unless you have reviewed the resources and namespaces first.

### Troubleshooting commands

```bash
kubectl get events --sort-by=.metadata.creationTimestamp
kubectl describe pod <pod-name>
kubectl logs <pod-name>
kubectl get pvc
```

These commands help distinguish scheduling/image-pull problems, application errors, and persistent-volume binding issues.

### Cleanup

Delete only the resources created for the exercise, using the same manifest files or the specific resource names:

```bash
kubectl delete -f <manifest-file>.yaml
```

Review the resources first so you do not remove workloads that belong to another exercise or namespace.

### Learning note

Commands above are generic Kubernetes workflows. Manifest names and resource names depend on the files in each project directory; inspect those files before running commands.
