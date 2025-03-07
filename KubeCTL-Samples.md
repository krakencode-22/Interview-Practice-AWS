<<<<<<< HEAD
# Kubernetes CLI (`kubectl`) Interview Questions and Answers (1-10)
=======
# Kubernetes Interview Questions and Answers (1-10)
>>>>>>> d19fdf785ff747a2069538c7883eba97552c2f95

<<<<<<< HEAD
---

### **1. How do you list all Pods in a namespace?**
**Answer:**  
Use the following command:  
`kubectl get pods -n <namespace>`  
Replace `<namespace>` with the desired namespace. To list Pods in all namespaces, use:  
`kubectl get pods --all-namespaces`

---

### **2. How do you describe a specific Pod?**
**Answer:**  
Use the following command:  
`kubectl describe pod <pod-name> -n <namespace>`  
Replace `<pod-name>` and `<namespace>` with the Pod name and namespace, respectively.

---

### **3. How do you create a resource from a YAML file?**
**Answer:**  
Use the following command:  
`kubectl apply -f <filename.yaml>`  
Replace `<filename.yaml>` with the path to your YAML file.

---

### **4. How do you delete a Pod?**
**Answer:**  
Use the following command:  
`kubectl delete pod <pod-name> -n <namespace>`  
Replace `<pod-name>` and `<namespace>` with the Pod name and namespace, respectively.

---

### **5. How do you check the logs of a specific Pod?**
**Answer:**  
Use the following command:  

`kubectl logs <pod-name> -n <namespace>`  
Replace `<pod-name>` and `<namespace>` with the Pod name and namespace, respectively. To stream logs in real-time, add the `-f` flag:  
`kubectl logs -f <pod-name> -n <namespace>`

---

### **6. How do you execute a command inside a running Pod?**
**Answer:**  
Use the following command:  
`kubectl exec -it <pod-name> -n <namespace> -- <command>`  
Replace `<pod-name>`, `<namespace>`, and `<command>` with the Pod name, namespace, and the command you want to execute, respectively. For example:  
`kubectl exec -it my-pod -n my-namespace -- /bin/sh`

---

### **7. How do you scale a Deployment?**
**Answer:**  
Use the following command:  
`kubectl scale deployment <deployment-name> --replicas=<number> -n <namespace>`  
Replace `<deployment-name>`, `<number>`, and `<namespace>` with the Deployment name, desired replica count, and namespace, respectively.

---

### **8. How do you edit a resource (e.g., Deployment) directly in the cluster?**
**Answer:**  
Use the following command:  
`kubectl edit deployment <deployment-name> -n <namespace>`  
Replace `<deployment-name>` and `<namespace>` with the Deployment name and namespace, respectively. This opens the resource in your default text editor.

---

### **9. How do you check the status of all nodes in the cluster?**
**Answer:**  
Use the following command:  
`kubectl get nodes`  
This lists all nodes and their status (e.g., Ready, NotReady).

---

### **10. How do you port-forward to a specific Pod?**
**Answer:**  
Use the following command:  
`kubectl port-forward <pod-name> <local-port>:<pod-port> -n <namespace>`  
Replace `<pod-name>`, `<local-port>`, `<pod-port>`, and `<namespace>` with the Pod name, local port, Pod port, and namespace, respectively. For example:  
`kubectl port-forward my-pod 8080:80 -n my-namespace`

---

# **Tips for Interviewees:**
- Practice these commands in a real Kubernetes environment to build muscle memory.
- Use `kubectl --help` or `kubectl <command> --help` for quick reference during interviews.
- Focus on understanding the purpose of each command and its flags.
=======
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
>>>>>>> d19fdf785ff747a2069538c7883eba97552c2f95