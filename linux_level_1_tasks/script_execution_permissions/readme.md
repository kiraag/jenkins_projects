## In a bid to automate backup processes, the xFusionCorp Industries sysadmin team has developed a new bash script named `xfusioncorp.sh`. While the script has been distributed to all necessary servers, it lacks executable permissions on `App Server 3` within the Stratos Datacenter.

## Your task is to grant executable permissions to the `/tmp/xfusioncorp.sh` script on `App Server 3`. Additionally, ensure that all users have the capability to execute it.

---

## To grant executable permissions to the `/tmp/xfusioncorp.sh` script on `App Server 3` and ensure that all users have the capability to execute it, follow these steps:

## Steps

### 1. Log in to App Server 3: 
Make sure you are logged into App Server 3 within the Stratos Datacenter.

`ssh <user_name>@<app_server_ip>`

### 2. Change Permissions:
Use the chmod command to grant executable permissions to all users for the script:

`sudo chmod a+rx /tmp/xfusioncorp.sh`

 - `a+rx` means "add read and execute permissions for all users (user, group, and others)."

### 3. Verify the Permissions:
After applying the command, verify that the permissions are correctly set:

`ls -l /tmp/xfusioncorp.sh`

You should see the following permissions:

`-r-xr-xr-x 1 user group size date /tmp/xfusioncorp.sh`

This means the script now has read `(r)` and execute `(x)` permissions for the owner, group, and others.

By adding the `r` permission, users can read the file, and with the `x` permission, they can execute the script.


