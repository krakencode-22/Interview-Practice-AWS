# Kubernetes Interview Questions and Answers (1-10)

---

### **1. What is `kubectl`, and what is it used for? What is the command `kubectl` and its syntax?**
**Answer:**  
`kubectl` is the command-line tool for interacting with Kubernetes clusters. It’s used to deploy, inspect, and manage applications.  
**Syntax:**  
`kubectl [command] [resource] [flags]`

---

### **2. What is a `kubelet`, and what are its uses?**
**Answer:**  
The `kubelet` is an agent running on each node. It ensures containers are running in Pods by communicating with the control plane and managing container lifecycle.

---

### **3. What do you understand by a node in Kubernetes? What does the node status contain?**
**Answer:**  
A **node** is a worker machine (physical or virtual) in Kubernetes. Node status includes **conditions** (e.g., Ready, MemoryPressure), **capacity**, and **allocatable resources**.

---

### **4. Explain Kubernetes architecture with a neat diagram. What are the different components of Kubernetes architecture and architecture layers of Kubernetes?**
**Answer:**  
Kubernetes architecture consists of:  
- **Control Plane:** API Server, Scheduler, Controller Manager, etcd.  
- **Worker Nodes:** Kubelet, kube-proxy, container runtime.  
- **Layers:** Infrastructure, Control Plane, Application.  
*(Note: Use a diagram tool to visualize this.)*

---

### **5. What do you understand by `kube-proxy`?**
**Answer:**  
`kube-proxy` is a network proxy running on each node. It maintains network rules to enable communication to and from Pods, using IP tables or IPVS.

---

### **6. Can you brief on the working and the process runs on the master node in Kubernetes?**
**Answer:**  
The master node runs:  
- **API Server:** Exposes the Kubernetes API.  
- **Scheduler:** Assigns Pods to nodes.  
- **Controller Manager:** Manages controllers (e.g., Node, ReplicaSet).  
- **etcd:** Stores cluster state.

---

### **7. What is the role of `kube-apiserver` and `kube-scheduler`?**
**Answer:**  
- **kube-apiserver:** Exposes the Kubernetes API and validates requests.  
- **kube-scheduler:** Assigns Pods to nodes based on resource requirements and constraints.

---

### **8. Can you brief about the Kubernetes controller manager and how it is useful?**
**Answer:**  
The **Controller Manager** runs controllers like Node, ReplicaSet, and Endpoint controllers. It ensures the cluster’s desired state matches the actual state.

---

### **9. What is an `etcd` in Kubernetes?**
**Answer:**  
`etcd` is a distributed key-value store used by Kubernetes to store cluster state, configuration, and metadata. It ensures consistency and high availability.

---

### **10. What do you know about Kubernetes service? What are the different types of services in Kubernetes?**
**Answer:**  
A **Service** provides stable network access to Pods. Types:  
- **ClusterIP:** Internal access.  
- **NodePort:** External access via node IP.  
- **LoadBalancer:** External access via cloud provider’s load balancer.  
- **ExternalName:** Maps to an external DNS name.

---

# **Tips for Interviewees:**
- Practice answering these questions concisely (3-6 seconds).
- Use diagrams for architecture questions to enhance clarity.
- Focus on both high-level concepts and technical details.