# Ansible Playbooks

This folder contains Ansible configuration for managing the server `sv1.cservices.co.il`.

## Files

- `inventory.ini` defines the target hosts.
- `encrypted_ubuntu_setup.yml` installing encrypted ubuntu 22.04 with hezner's installimage script from rescue.
- `k8s_setup.yml` installing and configuring untainted k8s single control plane node with cri-o and flunnel.
- `encrypted_ngf_setup.yml` installing metalLb, cert-manger and nginx gateway fabric and deploys let's encrypt signed tls loadbalanced (failover ip) gateway

## Usage

### Activate the virtual environment:
```
source .venv/bin/activate    # For Linux / macOS
```
```
.venv\Scripts\activate     # For Windows (if relevant)
```

Upgrade pip (recommended)
```
pip install --upgrade pip
```
Install project dependencies
```
pip install -r requirements.txt
```

### Run the playbooks from this directory with:

```bash
eval $(ssh-agent -s)
ssh-add ~/.ssh/id_ed25519
ansible-playbook -i inventory.ini encrypted_ubuntu_setup.yml
ansible-playbook -i inventory.ini k8s_setup.yml 
ansible-playbook -i inventory.ini encrypted_ngf_setup.yml
```