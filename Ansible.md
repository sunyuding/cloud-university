# Ansible
Ansible is an automation platform
- YAML
- Python

Use Cases
- Configuration Management
- Security Deployment
- Orchestration

GitHub: https://github.com/ansible/ansible

## Installation
[Installation Guide](https://docs.ansible.com/ansible/latest/installation_guide/index.html#installation-guide)

```bash
# the most common and preferred way of installation
$ pip install ansible

# install the epel-release RPM if needed on CentOS, RHEL
$ sudo yum install ansible

# you will need the PPA repo configured
$ sudo apt-get install ansible
```

## Ad-Hoc

## Playbook
**Plays** are ordered sets of tasks to execute against host selections from your inventory.

A **playbook** is a file containing one or more plays.

```
$ ansible-playbook -i hosts <YAML file name>
```

### YAML

### Variable

## Role
**Roles** are a packages of closely related Ansible content that can be shared more easily than plays alone.

### Ansible Galaxy
**Ansible Galaxy** is the place to share the **roles**.

Create a role.
```
$ ansible-galaxy init <role name>
```

### Breaking an Existing Playbook into a Role

## Vault
The “**Vault**” is a feature of **Ansible** that allows you to keep sensitive data such as passwords or keys protected at rest, rather than as plaintext in playbooks or roles. These vaults can then be distributed or placed in source control.

### ANSIBLE_VAULT_PASSWORD_FILE

The vault password file to use. Equivalent to –vault-password-file or –vault-id

See also [DEFAULT_VAULT_PASSWORD_FILE](https://docs.ansible.com/ansible/latest/reference_appendices/config.html?highlight=vault_password_file#default-vault-password-file)

### ansible-vault

## Reference
- [ ] [Ansible Configuration Settings](https://docs.ansible.com/ansible/latest/reference_appendices/config.html?highlight=vault_password_file#default-vault-password-file)