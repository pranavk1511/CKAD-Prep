# Kubernetes Interview Questions

## 1. What Is the Difference Between Docker and Kubernetes?

- **Docker** is a containerization platform, whereas **Kubernetes** is a container orchestration platform.
- Kubernetes can run independently of Docker.
- Kubernetes adds features such as:
  1. **Auto-healing**: Automatically restarts failed containers or nodes.
  2. **Load balancing**: Balances traffic between pods.
  3. **Enterprise-level orchestration**: Offers sophisticated tools for managing large-scale containerized applications.

---

## 2. What Are the Main Components of Kubernetes Architecture?

### Control Plane:
1. **API Server**: The entry point for all administrative tasks in Kubernetes.
2. **etcd**: A key-value store that holds all cluster data for Kubernetes.
3. **Scheduler**: Assigns workloads to specific nodes in the cluster.
4. **Controller Manager**: Manages different controllers like ReplicaSet and Replication Controller.
5. **Cloud Control Manager**: Manages communication with the cloud provider.

### Data Plane:
1. **kube-proxy**: Manages network rules on each node and helps in network communication.
2. **kubelet**: Ensures containers are running in a pod as expected.
3. **Container Runtime**: Software responsible for running containers, like Docker, containerd, etc.

---

## 3. What Is the Difference Between Docker Swarm and Kubernetes?

- **Kubernetes** can work with multiple container runtimes (e.g., Docker, containerd, etc.).
- **Docker Swarm** is limited to Docker as its container runtime.

---

## 4. What Is the Difference Between a Pod and a Docker Container?

- A **Pod** is an abstraction over a Docker container, providing a higher level of configuration and metadata.
- A **Pod** can contain one or more containers.
- Pods include additional details like **labels**, **selectors**, and other metadata, allowing for replication and orchestration.

---

## 5. What Is a Namespace in Kubernetes?

- A **Namespace** in Kubernetes is an environment created for Kubernetes entities like pods, services, etc., acting like a virtual cluster.
- The default namespace is called **"default"**.
- Namespaces help isolate resources and create separate environments within a single Kubernetes cluster.

---

## 6. What Is the Role of kube-proxy?

- **kube-proxy** maintains the network rules that allow communication between different services and pods.
- It ensures that newly deployed resources are accessible by maintaining their IP addresses.

---

## 7. What Does a Service Do? What Are the Types of Services?

### What a Service Does:
1. **Load Balancing**: Distributes traffic across multiple pods.
2. **Expose the Cluster to Outside Networking**: Allows external access to the cluster resources when needed.
3. **Service Discovery**: Identifies and routes traffic to appropriate pods using labels and selectors.

### Types of Services:
1. **LoadBalancer**: Exposes the service to the external world.
2. **NodePort**: Opens a specific port on all nodes to expose the service.
3. **ClusterIP**: Exposes the service only within the cluster, making it internal-facing.

---

## 8. What Is kubelet?

- **kubelet** manages the lifecycle of containers in a pod.
- It communicates with the Kubernetes API server and ensures that the desired state of the pod (defined in the configuration) matches the actual state.
