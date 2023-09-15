# Ansible Galaxy

## Purpose
In this exercise, you will benefit of roles others have made by using [Ansible Galaxy](https://docs.ansible.com/ansible/latest/galaxy/user_guide.html). This will reveal the real power of roles! 

You will install `docker` on one of the target machines using a role provided in the Ansible Galaxy community.

## Steps

1. login via ssh to one of the target machines and verify that docker is _not_ installed.
```shell
ssh osboxes@<ip address>
docker --version
```

2. Navigate in the browser to https://galaxy.ansible.com/.

3. Find the `docker` role from **geerlingguy**.

4. Install the role in the directory where you will create your playbooks (roles-path). Be patient, this can take some minutes.
```shell
ansible-galaxy install --roles-path . namespace.role_name
```

5. Check the list of installed roles:
```shell
ansible-galaxy list --roles-path .
```

6. Create a playbook which installs docker on one of the targets using this installed role.

7. Login via ssh to one of the target machines and verify that docker is installed.

