## Introduction

This repository contains Ansible playbooks for automating the configuration, deployment, and management of Story Node.

## Prerequistes

Before using the Ansible playbooks in this repository, ensure the following prerequisites are met:
-	Ansible: Installed on your local machine or control node. Follow Ansible installation guide for more details.
- SSH Access: Ensure passwordless SSH access is configured between your control node and the managed nodes (target hosts).
- Inventory: Update the inventory file with the details of the hosts or groups you intend to manage.
- Python: Installed on the managed nodes.

### Setup and Installation
1. Install Ansible
```
pip install ansible
```
2. Clone the repository
```
git clone <repository>
cd <repository>
```

3. Copy inventory
```
cp inventory.ini.example inventory.ini
```

4. Configure inventory
- `node_ip`
- `ssh_user`
- `ssh_group`
- `ssh_port`
- `ssh_path`
- `remote_user_dir`

### Features
1. Instal and Luanch the node
```
ansible-playbook main.yaml
```

2. Upgrade
- You can manually use the inline var
```
ansible-playbook upgrade.yaml -e "story_version=$story_version" -e "geth_version=$geth_version"
```
- or change the value in `story.yaml`


3. Recovery the node from the snapshot
- You can manually use the inline var
```
ansible-playbook recovery_from_snapshot.yaml -e "story_snapshot_url=$story_snapshot_url" -e "geth_snapshot_url=$geth_snapshot_url"
```


