# Ansible Playbooks

This folder contains Ansible configuration for managing the server `sv1.cservices.co.il`.

## Files

- `inventory.ini` defines the target hosts.
- `install_encrypted_ubuntu_from_rescue.yml` installing encrypted ubuntu 22.04 with hezner's installimage script from rescue.
- `templates/setup.conf.j2` is a templated version of `setup.conf` used during installation.

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

### Run the playbook from this directory with:

```bash
eval $(ssh-agent -s)
ssh-add ~/.ssh/id_ed25519
ansible-playbook -i inventory.ini install_encrypted_ubuntu_from_rescue.yml
```