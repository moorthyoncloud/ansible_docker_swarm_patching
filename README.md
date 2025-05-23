# ansible_docker_swarm_patching
🔧 Docker Swarm Node Patching with Ansible
This Ansible playbook automates the safe and sequential patching of Docker Swarm manager and worker nodes on YUM-based systems (e.g., RHEL, CentOS, Rocky Linux).

🚀 Features
✅ Drains each node before patching
✅ Applies system updates using yum
✅ Logs updated packages and timestamps to a local file
✅ Reboots nodes only if updates were applied
✅ Waits for nodes to come back online
✅ Performs a Docker health check
✅ Sets the node back to active in the Swarm
✅ Logs patching status to patch_swarm_nodes.log on the control machine
