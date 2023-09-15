# Setup Environment

## Purpose
This exercise will setup the environment.
The complete setup is described [here](https://mydeveloperplanet.com/2022/05/04/how-to-setup-an-ansible-test-environment/).

## Steps
1. Start the Controller and the Target machines.

2. Login to the Controller:
   * username: osboxes
   * password: osboxes.org

3. Retrieve the IP addresses of the Target machines.
At the bottom of the VBox screen, hover over the network icon.

4. Open a Terminal window and connect via ssh to both target machines.

```shell
ssh osboxes@<ip address>
```
5. Answer `yes` when asked to continue connecting.
6. `exit`
