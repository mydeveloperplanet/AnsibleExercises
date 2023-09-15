# Vault

## Purpose
In this exercise you will learn about Ansible Vault in order to encrypt sensitive information, like passwords.

## Steps

1. Create in the directory of the target machines a file named `vault`.

2. Copy the `ansible_ssh_pass` variable to this `vault` file.

3. Rename the variable in the vault file to `vault_ansible_ssh_pass`.

4. Replace the plain text password in the `vars` file with the variable name as defined in the vault file ([jinja2 syntax](https://jinja.palletsprojects.com/en/3.1.x/) is used here).
```yaml
"{{ vault_ansible_ssh_pass }}"
```

5. Encrypt the vault file with a password (do not forget this password!).
```shell
ansible-vault encrypt inventory/host_vars/<machine name>/vault
```

6. Try to ping the machines with Ansible.
The following error will be shown:
```shell
ERROR! Attempting to decrypt but no vault secrets found
```

7. Add the parameter `--ask-vault-pass`.
The ping-command should be successful now.

More information about vault can be found here: https://docs.ansible.com/ansible/latest/vault_guide/index.html