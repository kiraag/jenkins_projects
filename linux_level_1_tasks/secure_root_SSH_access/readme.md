## Following security audits, the xFusionCorp Industries security team has rolled out new protocols, including the restriction of direct root SSH login.                                                                                                                           Your task is to disable direct SSH root login on all app servers within the Stratos Datacenter.

---
## To disable direct SSH root login on all app servers within the Stratos Datacenter, you need to modify the SSH configuration file on each server. Here’s a step-by-step guide to accomplish this:

### Step 1: Access the App Servers
1. SSH into each app server as a user with sudo privileges. For example:

`ssh your_user@app_server_ip`

Replace `your_user` with your non-root username and `app_server_ip` with the IP address of the server.

### Step 2: Edit the SSH Configuration File
2. Open the SSH configuration file using a text editor like `vi` or `nano`:

`sudo vi /etc/ssh/sshd_config`

3. Find the line that specifies PermitRootLogin. It may look like this:

`#PermitRootLogin yes`

4. Uncomment and modify the line to disable root login:

`PermitRootLogin no`

-If the line is commented (starts with `#`), remove the `#`.

-Change `yes` to `no`.

### Step 3: Restart the SSH Service
5. Restart the SSH service to apply the changes:

`sudo systemctl restart sshd`
        
        or
`sudo service sshd restart`

### Step 4: Verify the Configuration
6. Test the SSH login to ensure that root access is disabled:

 -Try to SSH into the server as root

`ssh root@app_server_ip`

 -It should now deny the connection with a message like Permission denied.

### Step 5: Repeat on All App Servers
7. Repeat these steps for each app server within the Stratos Datacenter to ensure that direct root SSH login is disabled across all servers.

### Summary
 -Access each app server as a non-root user.
 
 -Edit the `/etc/ssh/sshd_config` file to set `PermitRootLogin` to `no`.
 
 -Restart the SSH service to apply changes.
 
 -Verify that root login is disabled.
 
 ### This process ensures enhanced security by restricting direct SSH access as the root user, which is critical for maintaining a secure environment.
























