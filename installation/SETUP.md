# Kubespray HA Cluster Installation

`Kubespray` is an open-source project used to automate the installation and configuration of Kubernetes clusters using Ansible. This guide explains how to set up a **Highly Available (HA)** Kubernetes cluster using Kubespray.

---

## 📋 Requirements

### Infrastructure

* **3 Control Plane (Master) Nodes** – minimum **8 GB RAM** each
* **1–2 Worker Nodes** – minimum **4 GB RAM** each

### Software

* Python 3
* Pip
* Ansible (installed via `requirements.txt`)
* SSH access to all nodes

---

## 🚀 Installation Steps

### 1. Clone the Kubespray Repository

```bash
git clone https://github.com/kubernetes-sigs/kubespray
```

---

### 2. Remove Git Metadata (Optional)

If you want to manage Kubespray as part of your own repository:

```bash
rm -rf .git .github .gitlab-ci
```

---

### 3. Install Kubespray Dependencies

```bash
cd kubespray
pip install -r requirements.txt
```

---

### 4. Configure Inventory

Edit the inventory file located at:

```
kubespray/inventory/sample/inventory.ini
```

#### Example Inventory Configuration

```ini
[all:vars]
ansible_user=vuthy
ansible_ssh_extra_args='-o StrictHostKeyChecking=no -o UserKnownHostsFile=/dev/null'
ansible_python_interpreter=/usr/bin/python3

[kube_control_plane]
node1 ansible_host=35.213.173.163 ansible_connection=local
node2 ansible_host=34.142.148.247
node3 ansible_host=34.87.32.144

[etcd:children]
kube_control_plane

[kube_node]
node4 ansible_host=34.92.94.59
node5 ansible_host=34.96.233.157
```

---

### 5. Enable Kubernetes Add-ons

Edit the add-ons configuration file:

```
kubespray/inventory/sample/group_vars/k8s_cluster/addons.yml
```

```yaml
dashboard_enabled: true
helm_enabled: true
metrics_server_enabled: true
ingress_nginx_enabled: true
cert_manager_enabled: true
argocd_enabled: true
```

---

### 6. Deploy the HA Kubernetes Cluster

```bash
ansible-playbook -b -v -i inventory/sample/inventory.ini cluster.yml
```

### Reset / Destroy the Cluster

```bash
ansible-playbook -b -v -i inventory/sample/inventory.ini reset.yml
```

---

## ⚡ Optional: Use a Justfile

To simplify repeated commands, you can use a `Justfile`.

```makefile
setup-cluster:
    echo "Bringing up the HA Kubernetes cluster..."
    ansible-playbook -b -v -i inventory/sample/inventory.ini cluster.yml

destroy-cluster:
    echo "Resetting the HA Kubernetes cluster..."
    ansible-playbook -b -v -i inventory/sample/inventory.ini reset.yml
```

---

## ✅ Verify Installation

After successful installation:

```bash
sudo kubectl get nodes
sudo kubectl get nodes -o wide
sudo kubectl get pods -A
```

---

## 🔑 Use `kubectl` Without `sudo`

```bash
mkdir -p $HOME/.kube
sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config
sudo chown $(id -u):$(id -g) $HOME/.kube/config
```

Now you can run:

```bash
kubectl get nodes
```

---

## 📌 Notes

* Ensure all nodes can communicate over the network.
* Passwordless SSH access is recommended.
* For production, consider using a load balancer in front of control plane nodes.

---

🎉 **Your HA Kubernetes cluster with Kubespray is ready!**
