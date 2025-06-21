# Ansible Playbooks

This folder contains Ansible configuration for managing the server `sv1.cservices.co.il`.

## Files

- `inventory.ini` defines the target hosts.
- `playbook.yml` provisions the server using the same steps as the original `v2.sh` setup script.
- `templates/setup.conf.j2` is a templated version of `setup.conf` used during installation.

## Usage

Run the playbook from this directory with:

```bash
eval $(ssh-agent -s)
ssh-add ~/.ssh/id_ed25519
ansible-playbook playbook.yml -i inventory.ini
```

## Depedencies

- expect (apt)