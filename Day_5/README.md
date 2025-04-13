### 🚀 **Kubernetes Overview**

**Step 1:**  
Create a **jump server** (or bastion host) and connect to the server instance.

**Step 2:**  
Install the necessary tools: `kubectl`, `ecsctl`, and `awscli`.

### Commands:

```bash
sudo su
vi cluster.sh
  # Paste the installation script for Kubernetes and dependencies from GitHub.
chmod 777 cluster.sh
sh cluster.sh
:wq
aws configure  # Configure AWS CLI by creating a user and using access key and secret key.
eksctl
eksctl create cluster --name sudhama-cluster --version 1.31 --region us-east-1 --nodegroup-name test-linux --node-type t2.micro --nodes 3 --nodes-min 3 --nodes-max 5 --managed
snap install kubectl --classic
aws eks update-kubeconfig --name sudhama-cluster --region us-east-1
kubectl get nodes  # To see the list of nodes.
```

Once connected:

```bash
git clone <repository_url>
ls
cd <repo_folder>
kubectl apply -f pod.yaml
kubectl get pods
kubectl get pods -o wide
kubectl describe pod sample-pod
```
---

**What is Kubernetes?**  
Kubernetes is a powerful container orchestration tool that automates deployment, scaling, and management of containerized applications. It manages a cluster of nodes, ensuring that your applications run smoothly, even in large-scale environments.

---

### **Steps to Set Up Kubernetes** 🌐

1. **Create a Jump Server (Bastion Host)** 🌐  
   First, set up a jump server that will act as the gateway to access your Kubernetes cluster.

2. **Install Necessary Tools** 🛠️  
   - Install `kubectl`, `ecsctl`, and `awscli` for managing the Kubernetes environment.
   - Configure your AWS CLI with `aws configure` (Enter Access Key & Secret Key).

---

### **Kubernetes Cluster Components** 🖧

#### 1. **Master Node Components** 👑
- **API Server** 🖥️: The "brain" of the cluster. It manages everything, including scaling and load balancing.
- **ETCD** 📚: A key-value store for all cluster data.
- **Controller Manager** 🔧: Monitors and ensures the desired state of your applications.
- **Scheduler** 📅: Decides where to place Pods (the smallest deployable units).

#### 2. **Worker Node Components** 🧑‍💻
- **Kubelet** 🔄: Responsible for creating and managing Pods in the worker node.
- **Container Runtime** 🛠️: Like Docker, it runs and manages containers.
- **Kube-Proxy** 🌐: A networking component that manages access to the application over the internet.

---

### **Cluster Types** 🏗️

1. **On-Premises Cluster** 🏢  
   Managed by your team, including handling downtime and troubleshooting.
  
2. **Cloud Managed Cluster (EKS)** ☁️  
   Managed by AWS, reducing the burden of maintenance.

---

### **Important Kubernetes Concepts** 💡

1. **Pod** 🏃‍♂️: The smallest deployable unit in Kubernetes, containing containers.
2. **Scaling** 📈:  
   - **Horizontal Scaling** ➡️ Adding more nodes.
   - **Vertical Scaling** ⬆️ Increasing node resources.
3. **Self-Healing** 🔄: Automatically replaces failed containers or nodes.

---

### **Kubernetes Architecture in Detail** 🏰

**Master Node** 👑  
- The **API Server** is the main point of interaction for managing the Kubernetes cluster.
- **ETCD** stores the configuration and state.
- **Controller** monitors the cluster and ensures the desired state is maintained.
- **Scheduler** assigns tasks (Pods) to the worker nodes.

**Worker Node** 🧑‍💻  
- **Kubelet**: Ensures the Pods are running as expected.
- **Container Runtime**: Manages containers on the node.
- **Kube-Proxy**: Handles network routing for Pods.

---

### **Kubernetes Resource Units** 🧮

- **CPU** 💻: 1 CPU = 1000 millicores (m).
- **Memory** 🧠: 1 GB = 1024 MB.

---