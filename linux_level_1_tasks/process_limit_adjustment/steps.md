In the Stratos Datacenter, our Storage server is encountering performance degradation due to excessive processes held by the nfsuser user. To mitigate this issue, we need to enforce limitations on its maximum processes. Please set the maximum process limits as specified below:

a. Set the soft limit to 1024

b. Set the hard limit to 2026
---

## To set the maximum process limits for the nfsuser user on the Storage server in the Stratos Datacenter, you can follow these steps:

### 1. Access the Storage server: 

Log in via SSH

```bash
ssh username@server-ip
```

### 2. Edit the limits configuration file: 

Open the `/etc/security/limits.conf` file with a text editor (you may need superuser privileges):

```bash
sudo vi /etc/security/limits.conf
```

### 3. Add the limits for nfsuser: 

Add the following lines at the end of the file to set the soft and hard limits:

```bash
nfsuser soft nproc 1024
nfsuser hard nproc 2026
```

Save and exit: If you're using `nano`, save the file with `CTRL + O`, press `Enter`, and exit with `CTRL + X`.

### 4. Verify the changes:

To ensure that the limits are applied, you can check by using the `ulimit` command after switching to the nfsuser account:

```bash
sudo su - nfsuser
ulimit -Sn  # Should show 1024
ulimit -Hn  # Should show 2026
```

### 5. Reboot or re-login:

The changes will take effect after the user logs out and logs back in, or after a system reboot.

 ## NOTE:

  - We cannot reboot the server, but we can finish the task.



