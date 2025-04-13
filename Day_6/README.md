

---

### **Kubernetes Commands & Concepts (Day 6)** 🧑‍💻

1. **Managing Namespaces** 🌐  
   Kubernetes allows you to partition a cluster into multiple isolated environments using **Namespaces**.

   - **List namespaces:**
     ```bash
     kubectl get namespace
     ```

   - **Show all resources in `kube-system` namespace:**
     ```bash
     kubectl get all -n kube-system
     ```

   - **Create a custom namespace:**
     ```bash
     kubectl create ns sudhama-ns
     ```

   - **List all namespaces:**
     ```bash
     kubectl get ns
     ```

---

2. **Running Pods in a Namespace** 🚀

   - **Run a pod in the custom namespace `sudhama-ns` using the `nginx` image:**
     ```bash
     kubectl run test-pod --image=nginx --port=80 -n sudhama-ns
     ```

   - **Check if the pod was created in the `sudhama-ns` namespace:**
     ```bash
     kubectl get pods -n sudhama-ns
     ```

   - **Delete the pod:**
     ```bash
     kubectl delete pod test-pod -n sudhama-ns
     ```

---

3. **Replica Set (rs.yaml)** 🔄

   - **Create a ReplicaSet (`rs.yaml`) file in your editor.**
   
   - **Clone the repository to get `rs.yaml`:**
     ```bash
     git clone https://github.com/Sudhama-bhat/sudhama-k8s-manifests.git
     ```

   - **Apply the ReplicaSet configuration:**
     ```bash
     kubectl apply -f rs.yaml
     ```

   - **Check the status of Pods and ReplicaSets:**
     ```bash
     kubectl get pods -n sudhama-ns
     kubectl get rs -n sudhama-ns
     ```

   - **If a Pod is pending, check the detailed description:**
     ```bash
     kubectl describe pod -n sudhama-ns <pod-name>
     ```

   - **Delete the ReplicaSet:**
     ```bash
     kubectl delete rs cart-page-rs -n sudhama-ns
     ```

---

4. **Deployments** 🚀

   - **Deploy using a `deployment.yaml` file:**
     ```bash
     kubectl apply -f deployment.yaml -n sudhama-ns
     ```

   - **Check the deployment and pod status:**
     ```bash
     kubectl get deployments -n sudhama-ns
     kubectl get pods -o wide -n sudhama-ns
     ```

---

5. **Services** 🌐

   - **Create a Service to expose the application:**
     ```bash
     kubectl apply -f service.yaml
     ```

   - **If you face issues with resources, specify the namespace:**
     ```bash
     kubectl apply -f name.yaml -n sudhama-ns
     ```

   - **Get the URL to access the service (use with port number):**
     ```bash
     kubectl get svc -n sudhama-ns
     ```

---

### **Kubernetes Core Concepts** 📚

1. **What is a Namespace?** 🌏  
   A Namespace is a way to divide your cluster into isolated environments. It's useful when deploying multiple projects, ensuring they do not interfere with each other.

   - **Note:** Never deploy applications in the **default namespace** for production environments.

2. **Pod Failure Management** ⚠️

   - **Problems:**
     1. **Application Downtime** - To prevent downtime, attach controllers to Pods.
     2. **IP Address Changes** - Pods have dynamic IPs, and if they go down, the IP changes. To resolve this, use **Services** to create a static URL.
     3. **Data Loss** - When a pod fails, data may be lost. Use **Volumes** in Kubernetes to persist data.

3. **ReplicaSet** 🔄

   - A **ReplicaSet** ensures that a specified number of pod replicas are always running. However, it’s not recommended for **rollout and rollback operations**.

4. **Deployments** 🎯

   - **Deployment** is a higher-level abstraction that manages ReplicaSets and Pods. It's used for deploying applications in Kubernetes, allowing easy management of pod lifecycles and updates.

---

### **Kubernetes Services** 🛠️

There are three types of Services to expose your applications in Kubernetes:

1. **ClusterIP**: Exposes the service internally within the cluster.
2. **NodePort**: Exposes the service on each node’s IP at a static port.
3. **LoadBalancer**: Exposes the service externally using a load balancer.

---

### **Monitoring Kubernetes Applications** 📊

To ensure your application is running smoothly, use **monitoring tools** like **Prometheus** and **Grafana**.

1. **Prometheus**:  
   - It collects and stores time-series data (TSDB) and sends it to Grafana for visualization.
   
2. **Grafana**:  
   - Provides beautiful monitoring dashboards where you can visualize your application's performance metrics, including CPU usage, memory consumption, and node health.

---

### **Configuration Management** 🔧

- **Ansible** is a configuration management tool used to automate the setup, configuration, and management of Kubernetes resources.

---
