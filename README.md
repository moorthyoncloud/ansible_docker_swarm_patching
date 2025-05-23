# 🔧 Docker Swarm Node Patching with Ansible

This Ansible playbook automates the safe and sequential patching of Docker Swarm **manager** and **worker** nodes on **YUM-based systems** (e.g., RHEL, CentOS, Rocky Linux).

## 🚀 Features

- ✅ Drains each node before patching
- ✅ Applies system updates using `yum`
- ✅ Logs updated packages and timestamps to a local file
- ✅ Reboots nodes **only if updates were applied**
- ✅ Waits for nodes to come back online
- ✅ Performs a Docker health check
- ✅ Sets the node back to `active` in the Swarm
- ✅ Logs patching status to `patch_swarm_nodes.log` on the control machine

---

## 📁 Files

- `patch_swarm_nodes.yml` – The main playbook

---

## 🧩 Inventory Example (`hosts.ini`)
[swarm_nodes]
manager1
manager2
worker1
worker2

[manager_node]
manager1  # Used to run docker node update commands

## 🛠️ Usage

ansible-playbook -i hosts.ini patch_swarm_nodes.yml

Make sure:

You have SSH access to all nodes.
Docker Swarm is already initialized and nodes are part of the cluster.
The control machine has Ansible installed.

📄 Log Output

Logs are saved to patch_swarm_nodes.log in the directory where the playbook is run. Example:

worker1 - 2025-05-23T12:34:56Z - Updated packages: bash, curl, docker-ce

📬 Contributions & Feedback

Feel free to open issues or submit pull requests to improve this playbook!

Would you like me to generate a README.md file with this content for your GitHub repo?
