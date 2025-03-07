# Kubernetes CLI (`kubectl`) Interview Questions and Answers (1-10)

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