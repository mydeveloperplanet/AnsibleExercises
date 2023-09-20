# Roles

## Purpose
In this exercise, you will learn how to create roles for repetitive tasks. This exercise will restructure the previous Apache plays in order to make them reusable.
More information about roles can be found [here](https://docs.ansible.com/ansible/latest/playbook_guide/playbooks_reuse_roles.html#role-directory-structure).

In the first part of the exercise you will create a role for the Apache installation, in the second part of the exercise, you will make use of a variable in order to be able to dynamically change the behaviour of the role.

## Steps

1. Create a directory `roles`.

2. Create in directory `roles`, a directory with the name of the role (e.g. `webserver`).

3. Create in directory `webserver`, a directory `tasks`.
The resulting directory structure should be:
```shell
roles
 |__ webserver
          |__ tasks
```          

4. In directory `tasks`, create a file `main.yml` and copy the tasks from the latest playbook into this file.

5. Change the welcome message to something different, this way, you will be able to notice any difference when running the playbook.

6. Copy the contents of the last playbook into a new playbook.
Replace the tasks with a roles part.
```yaml
roles:
  - webserver
```

7. Run the playbook and check the welcome pages of both target machines.
The welcome message should have been changed to the new one.

8. Create a new role (e.g. `webserver-var`) similar to the `webserver` role.

9. Change the welcome message in order that it makes use of a variable (using Ninja2 syntax).

10. Create in the `roles/webserver-var/` directory a directory `defaults` and add a `main.yml` file.

11. Assign the variable with a sensible default message. E.g.
```yaml
hello_message: nice to meet you
```

12. Copy the previous created playbook and set a custom message by assigning the variable for one of the targets.
Note that the syntax is a bit different. It should be like:
```yaml
  roles:
    - role: webserver
      vars:
        hello_message: 'target2 says hello'
```

13. Run the playbook and check the welcome pages of both target machines.
One machine should show the default message, the other one the custom one.