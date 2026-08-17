# Install Docker (Ubuntu)

Update package information and install Docker:

```bash
sudo apt update
sudo apt install docker.io -y
```

Enable and start the Docker service:

```bash
sudo systemctl enable docker
sudo systemctl start docker
```

Verify Docker installation:

```bash
docker --version
docker ps
```

Allow the current user to run Docker without sudo:

```bash
sudo usermod -aG docker $USER
```

> **Note:** Log out and log back in (or reboot) after running the command for the changes to take effect.

---

# Install kubectl

Download the latest stable kubectl binary:

```bash
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
```

Make the binary executable:

```bash
chmod +x kubectl
```

Move kubectl to a directory in your PATH:

```bash
sudo mv kubectl /usr/local/bin/
```

Verify kubectl installation:

```bash
kubectl version --client
```

---

# Install Kind

Download the latest Kind binary:

```bash
curl -Lo ./kind https://kind.sigs.k8s.io/dl/latest/kind-linux-amd64
```

Make the binary executable:

```bash
chmod +x ./kind
```

Move Kind to a directory in your PATH:

```bash
sudo mv ./kind /usr/local/bin/kind
```

Verify Kind installation:

```bash
kind version
```

---

# Create Kubernetes Cluster

Create a Kubernetes cluster using Kind:

```bash
kind create cluster --name k8s-zero-to-hero
```

Verify cluster nodes:

```bash
kubectl get nodes
```

Expected output:

```bash
NAME                                 STATUS   ROLES           AGE   VERSION
k8s-zero-to-hero-control-plane       Ready    control-plane   1m    v1.xx.x
```

---

# Verify Cluster Information

```bash
kubectl cluster-info
kubectl get nodes
kubectl get namespaces
```

---

# Delete Cluster (Optional)

```bash
kind delete cluster --name k8s-zero-to-hero
```