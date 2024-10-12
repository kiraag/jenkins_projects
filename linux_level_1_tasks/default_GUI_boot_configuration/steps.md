With the installation of new tools on the app servers within the Stratos Datacenter, certain functionalities now necessitate `graphical user interface` `(GUI)` access.

Adjust the default runlevel on all App servers in Stratos Datacenter to enable GUI booting by default. It's imperative not to initiate a server reboot after completing this task.

---

## To change the default runlevel on all App servers in the Stratos Datacenter to enable GUI booting by default, you can follow these steps.

### 1.Access each App server: 

Log in to each server using SSH 

```bash
ssh user-name@server-ip
```

### 2. Change the default target: 

Use the following command to set the default target to `graphical`:

```bash
sudo systemctl set-default graphical.target
```

### 3. Verify the change: 

To ensure that the change has been applied, you can check the current default target with:

```bash
systemctl get-default
```

It should return `graphical.target`.


 - Repeat on all servers: Make sure to repeat these steps on each App server in the Stratos Datacenter.

### Note:

 - Do not reboot the servers after this change, as per the instruction.