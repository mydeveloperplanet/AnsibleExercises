# Install Apache Webserver

## Purpose
In this exercise, you will install Apache Webserver on both target machines.

## Steps

1. Create a playbook. Add a play in order to install Apache Webserver on one of the targets. Use the [apt-module](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/apt_module.html#ansible-collections-ansible-builtin-apt-module) for this. 
Take a look at the examples as a hint and ensure to update the cache before installing.

2. Execute the playbook and notice that it will not end successfully (keeps on 'hanging'). Do not break to early, installing does cost some time (few minutes)
Stop it with `CTRL+C`.

3. Problem is that you need sudo privileges for installing packages.
More information can be found [here](https://docs.ansible.com/ansible/latest/playbook_guide/playbooks_privilege_escalation.html). 

4. Add the `become: yes` parameter to the play.

5. Execute the playbook and add the argument `--ask-become-pass`. As an alternative solution, you can add `ansible_become_password` in the `vars` file of the target machine.

6. Notice that in the `PLAY RECAP` the changed parameter has value 1 (meaning, the play changed something on the machine).

7. Navigate in the browser on the host machine or on the controller machine to the webpage of Apache Webserver.
The Apache Default Page must be shown.
```
http://<ip address>
```

Alternative, use `curl` in the terminal:
```shell
curl http://<ip address>
```

8. Add another task to change the default page.
Use the [copy module](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/copy_module.html#ansible-collections-ansible-builtin-copy-module) in order to change the welcome page. The welcome page is located at: `/var/www/html/index.html`.

9. Execute the playbook again and notice that Apache is not installed again (because it is already installed).

10. Navigate to the welcome page in your browser and notice the default page is replaced with the contents you provided in the play.

11. Install Apache to the other target machine, change the welcome page with some other contents and run the playbook again.
Take again a closer look to the log and see which actions are skipped and which actions are executed.
12. Navigate in the browser to the ip address of the other machine and check whether you see the custom welcome page.