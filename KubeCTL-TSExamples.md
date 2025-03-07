### **1. How do you check the status of all nodes in the cluster?**
**Answer:**  
Use the following command:  
`kubectl get nodes`  
This shows the status of all nodes (e.g., Ready, NotReady). If a node is NotReady, investigate node-level issues like kubelet crashes or resource constraints.

---

### **2. How do you troubleshoot a Pod that is stuck in the "Pending" state?**
**Answer:**  
First, describe the Pod to identify the issue:  
`kubectl describe pod <pod-name> -n <namespace>`  
Look for events like insufficient resources, node affinity/taint issues, or missing PersistentVolumeClaims.

---

### **3. How do you check the logs of a specific container in a Pod?**
**Answer:**  
Use the following command:  
`kubectl logs <pod-name> -c <container-name> -n <namespace>`  
Replace `<pod-name>`, `<container-name>`, and `<namespace>` with the appropriate values. This helps identify application errors or misconfigurations.

---

### **4. How do you troubleshoot a Pod that is crashing repeatedly?**
**Answer:**  
First, check the Pod's logs:  
`kubectl logs <pod-name> -n <namespace>`  
Then, describe the Pod to check events:  
`kubectl describe pod <pod-name> -n <namespace>`  
Look for issues like failed probes, resource limits, or application crashes.

---

### **5. How do you check the resource usage (CPU/memory) of a Pod?**
**Answer:**  
Use the following command:  
`kubectl top pod <pod-name> -n <namespace>`  
This shows CPU and memory usage. If usage is high, check resource requests/limits in the Pod's YAML or scale the Deployment.

---

### **6. How do you troubleshoot a Service that is not routing traffic to Pods?**
**Answer:**  
First, check the Service's endpoints:  
`kubectl get endpoints <service-name> -n <namespace>`  
If no endpoints are listed, ensure the Pods have the correct labels and are running. Also, verify the Service's `selector` matches the Pod's labels.

---

### **7. How do you check the status of all Pods in a namespace?**
**Answer:**  
Use the following command:  
`kubectl get pods -n <namespace>`  
This lists all Pods and their status (e.g., Running, Pending, CrashLoopBackOff). Investigate any Pods not in the "Running" state.

---

### **8. How do you troubleshoot a Deployment that is not updating?**
**Answer:**  
First, check the Deployment's rollout status:  
`kubectl rollout status deployment/<deployment-name> -n <namespace>`  
If the rollout is stuck, describe the Deployment to check events:  
`kubectl describe deployment <deployment-name> -n <namespace>`  
Look for issues like image pull errors or resource constraints.

---

### **9. How do you check the events in a namespace to identify issues?**
**Answer:**  
Use the following command:  
`kubectl get events -n <namespace>`  
This shows recent events like Pod creation, scheduling, or failures. Look for warnings or errors that indicate underlying issues.

---

### **10. How do you troubleshoot a PersistentVolumeClaim (PVC) that is not bound?**
**Answer:**  
First, describe the PVC to check its status:  
`kubectl describe pvc <pvc-name> -n <namespace>`  
Look for events like no available PersistentVolume (PV) or storage class issues. Ensure the PVC's storage request matches available PVs.

---


### **Basic Commands (Beginner):**
- `create`: Create a resource from a file or from stdin.
- `expose`: Take a replication controller, service, deployment, or pod and expose it as a new Kubernetes service.
- `run`: Run a particular image on the cluster.
- `set`: Set specific features on objects.

### **Basic Commands (Intermediate):**
- `explain`: Get documentation for a resource.
- `get`: Display one or many resources.
- `edit`: Edit a resource on the server.
- `delete`: Delete resources by file names, stdin, resources and names, or by resources and label selector.

### **Deploy Commands:**
- `rollout`: Manage the rollout of a resource.
- `scale`: Set a new size for a deployment, replica set, or replication controller.
- `autoscale`: Auto-scale a deployment, replica set, stateful set, or replication controller.

### **Cluster Management Commands:**
- `certificate`: Modify certificate resources.
- `cluster-info`: Display cluster information.
- `top`: Display resource (CPU/memory) usage.
- `cordon`: Mark node as unschedulable.
- `uncordon`: Mark node as schedulable.
- `drain`: Drain node in preparation for maintenance.
- `taint`: Update the taints on one or more nodes.

### **Troubleshooting and Debugging Commands:**
- `describe`: Show details of a specific resource or group of resources.
- `logs`: Print the logs for a container in a pod.
- `attach`: Attach to a running container.
- `exec`: Execute a command in a container.
- `port-forward`: Forward one or more local ports to a pod.
- `proxy`: Run a proxy to the Kubernetes API server.
- `cp`: Copy files and directories to and from containers.
- `auth`: Inspect authorization.
- `debug`: Create debugging sessions for troubleshooting workloads and nodes.
- `events`: List events.



### **Advanced Commands:**
- `diff`: Diff the live version against a would-be applied version.
- `apply`: Apply a configuration to a resource by file name or stdin.
- `patch`: Update fields of a resource.
- `replace`: Replace a resource by file name or stdin.
- `wait`: Experimental: Wait for a specific condition on one or many resources.
- `kustomize`: Build a kustomization target from a directory or URL.

### **Settings Commands:**
- `label`: Update the labels on a resource.
- `annotate`: Update the annotations on a resource.
- `completion`: Output shell completion code for the specified shell (bash, zsh, fish, or powershell).

### **Subcommands provided by plugins:**
- (Plugin-specific commands)

### **Other Commands:**
- `api-resources`: Print the supported API resources on the server.
- `api-versions`: Print the supported API versions on the server, in the form of "group/version".
- `config`: Modify kubeconfig files.
- `plugin`: Provides utilities for interacting with plugins.
- `version`: Print the client and server version information.

---

# **Tips for Interviewees:**
- Practice these commands in a real Kubernetes environment to build muscle memory.
- Use `kubectl --help` or `kubectl <command> --help` for quick reference during interviews.
- Focus on understanding the purpose of each command and its flags.