# Kubernetes and Amazon EKS Interview Questions (Organized by Core Competency)

---

## **1. Kubernetes Basics**
### **Question 1:** What is Kubernetes, and why is it used?  
**Answer:** Kubernetes is an open-source container orchestration platform used to automate deployment, scaling, and management of containerized applications. It ensures high availability, scalability, and efficient resource utilization.

### **Question 2:** What is a **Pod** in Kubernetes, and how does it differ from a **Container**?  
**Answer:** A **Pod** is the smallest deployable unit in Kubernetes and can contain one or more containers. Containers within a Pod share the same network namespace, storage, and lifecycle. A **Container** is a runtime instance of an image that holds the application and its dependencies.

### **Question 3:** What is a **Node** in Kubernetes, and what are its types?  
**Answer:** A **Node** is a worker machine in Kubernetes, either physical or virtual. There are two types: **Worker Nodes** (run Pods) and **Master Nodes** (manage the cluster via components like the API server and scheduler).

---

## **2. Amazon EKS Overview**
### **Question 4:** What is **Amazon EKS**, and how does it simplify Kubernetes management?  
**Answer:** Amazon EKS (Elastic Kubernetes Service) is a managed Kubernetes service that handles control plane provisioning, scaling, and maintenance. It integrates with AWS services like IAM, VPC, and CloudWatch, simplifying cluster management and ensuring high availability.

### **Question 5:** What is **Amazon EKS**, and how does it differ from self-managed Kubernetes?  
**Answer:** Amazon EKS is a managed Kubernetes service that handles control plane provisioning, scaling, and maintenance. Unlike self-managed Kubernetes, EKS integrates with AWS services and ensures high availability with minimal operational overhead.

---

## **3. Kubernetes Components**
### **Question 6:** What is the role of the **kube-scheduler** in a Kubernetes cluster?  
**Answer:** The **kube-scheduler** assigns Pods to nodes based on resource requirements, node capacity, and constraints like taints, tolerations, and affinity rules. It ensures optimal placement of workloads across the cluster.

### **Question 7:** What is a **ConfigMap** in Kubernetes, and how is it used?  
**Answer:** A **ConfigMap** is used to store non-sensitive configuration data as key-value pairs. It decouples configuration from container images, allowing applications to access environment variables or configuration files.

### **Question 8:** What is a **Service** in Kubernetes, and what are its types?  
**Answer:** A **Service** provides stable network access to Pods. Types include **ClusterIP** (internal access), **NodePort** (external access via node IP), and **LoadBalancer** (external access via cloud provider’s load balancer).

---

## **4. Amazon EKS Networking**
### **Question 9:** How does **Amazon EKS** handle networking for Pods, and what is the role of the **VPC CNI plugin**?  
**Answer:** EKS uses the **VPC CNI plugin** to assign IP addresses from the VPC subnet directly to Pods. This enables native communication with AWS resources and integrates with security groups and network ACLs for fine-grained control.

### **Question 10:** How does **Amazon EKS** enforce network security for Pods?  
**Answer:** EKS uses **security groups** and **network ACLs** to control traffic to and from Pods. The **VPC CNI plugin** assigns Pods IPs from the VPC subnet, enabling native AWS security features.

---

## **5. Kubernetes Scaling**
### **Question 11:** What is the difference between **Horizontal Pod Autoscaler (HPA)** and **Vertical Pod Autoscaler (VPA)** in Kubernetes?  
**Answer:** **HPA** scales the number of Pods based on metrics like CPU or memory usage, while **VPA** adjusts the resource requests and limits (CPU/memory) of existing Pods. HPA is for stateless workloads; VPA optimizes resource usage.

### **Question 12:** How does the **Cluster Autoscaler** work in Kubernetes?  
**Answer:** The **Cluster Autoscaler** automatically adjusts the number of nodes in a cluster based on resource demands. It scales out when Pods cannot be scheduled due to insufficient resources and scales in when nodes are underutilized.

---

## **6. Amazon EKS Security**
### **Question 13:** How does **Amazon EKS** integrate with AWS Identity and Access Management (IAM) for cluster security?  
**Answer:** EKS uses **IAM roles for service accounts (IRSA)** to allow Pods to assume IAM roles. It leverages OIDC (OpenID Connect) to federate Kubernetes service accounts with IAM, enabling secure access to AWS resources.

### **Question 14:** How does **Amazon EKS** enforce network security for Pods?  
**Answer:** EKS uses **security groups** and **network ACLs** to control traffic to and from Pods. The **VPC CNI plugin** assigns Pods IPs from the VPC subnet, enabling native AWS security features.

---

## **7. Kubernetes Storage**
### **Question 15:** What is a **Persistent Volume (PV)** in Kubernetes, and how does it differ from a **Persistent Volume Claim (PVC)**?  
**Answer:** A **PV** is a piece of storage provisioned in the cluster, either manually or dynamically. A **PVC** is a request for storage by a user or application. PVCs bind to PVs, allowing Pods to consume storage independently of their lifecycle.

### **Question 16:** What is a **StorageClass** in Kubernetes, and how is it used?  
**Answer:** A **StorageClass** defines the type of storage (e.g., SSD, HDD) and provisioning parameters (e.g., AWS EBS, GP2). It enables dynamic provisioning of Persistent Volumes (PVs) when a Persistent Volume Claim (PVC) is created.

---

## **8. Amazon EKS Monitoring**
### **Question 17:** What AWS services can you use to monitor an **Amazon EKS** cluster, and what kind of data can you collect?  
**Answer:** Use **CloudWatch** for logs, metrics, and events; **CloudWatch Container Insights** for detailed performance data; and **AWS X-Ray** for tracing microservices. You can also use **Prometheus** for advanced monitoring.

### **Question 18:** How can you monitor application performance in **Amazon EKS**?  
**Answer:** Use **CloudWatch Container Insights** for metrics like CPU, memory, and network usage. Integrate **Prometheus** for advanced monitoring and **AWS X-Ray** for tracing and debugging microservices.

---

## **9. Kubernetes Deployments**
### **Question 19:** What is the purpose of a **Deployment** in Kubernetes, and how does it differ from a **StatefulSet**?  
**Answer:** A **Deployment** manages stateless applications, ensuring a specified number of Pod replicas are running and supporting rolling updates. A **StatefulSet** is for stateful applications, providing stable network identities and ordered Pod creation/deletion.

### **Question 20:** What is a **DaemonSet** in Kubernetes, and how is it different from a **Deployment**?  
**Answer:** A **DaemonSet** ensures a copy of a Pod runs on all (or specific) nodes in the cluster, ideal for node-level tasks like logging or monitoring. A **Deployment** manages stateless applications with a specified number of replicas.

---

# **Tips for Interviewees:**
- Practice answering these questions concisely (3-6 seconds).
- Focus on both high-level concepts and technical details.
- Use examples to demonstrate practical knowledge.
