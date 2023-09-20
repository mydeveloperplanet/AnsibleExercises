# Playbook

## Purpose
In this exercise, you will learn how to create a playbook which pings the target machines.

## Steps

1. Create a playbook yaml file.

2. Create in the playbook a play for each target machine (although this seems redundant, you could specify both hosts for the play).
The format of a play is:

```yaml
- name: <a name for this play>
  hosts: <the machine name>

  tasks:
    - name: <a name for the task>
      ansible.builtin.ping:

```

3. Execute the playbook. Note the logging where the plays and tasks are logged and take notice of each step and the `PLAY RECAP` at the bottom of the log.
```shell
ansible-playbook <name of the playbook> -i <path to the inventory file>
```

4. The list of all available modules can be found [here](https://docs.ansible.com/ansible/latest/collections/index_module.html). 

5. Crash the first play in the playbook. Add the parameter `data: crash` to the ping task.

6. Execute the playbook. Note that play 1 crashes and the playbook ends without executing the second play.

7. Inspect the log output.