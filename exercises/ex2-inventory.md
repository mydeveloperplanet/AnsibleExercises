# Inventory

## Purpose
In this exercise you will learn how to create an inventory and how to manage your machines.

## Steps

1. Create a directory `inventory` and add an `inventory.ini` file.

2. Add both targets to the inventory file. Choose any name you like for the targets.
E.g.
```yaml
target1
target2
```

3. Create a directory `host_vars` in directory `inventory` and add for each target a directory corresponding to the name you chose in 1.

4. Create inside each target directory a `vars` file with the following contents:
```yaml
ansible_host: <ip address>
ansible_connection: ssh
ansible_user: osboxes
ansible_ssh_pass: osboxes.org
```

5. Verify whether you are able to ping the target machines via Ansible.
```shell
ansible <target name> -m ping -i <path to the inventory file>
```

6. You should receive a success response, like:
```shell
target1 | SUCCESS => {
    "ansible_facts": {
        "discovered_interpreter_python": "/usr/bin/python3"
    },
    "changed": false,
    "ping": "pong"
}
```

7. Create a group containing both target machines in the inventory. Syntax is:
```yaml
[<group name>]
<machine names>
```

8. Verify whether the ping command can be executed for the group

9. Create a group of groups in the inventory. Syntax is:
```yaml
[<group name>:children]
<group names>
```

10. Verify whether the ping command can be executed for the group of groups.