# To create the nautilus_admin_users group and add the user kano across all App servers

To create the `nautilus_admin_users` group and add the user `kano` across all App servers in the Stratos Datacenter, you can follow these steps. The specific commands may vary depending on your operating system, but here’s a general approach for a Unix/Linux environment.

---

## Step-by-step Instructions

### 1. Create the Group:
You need to create the group `nautilus_admin_users`. This can usually be done using the `groupadd` command.

`sudo groupadd nautilus_admin_users`

### 2. Check for User Existence and Create User:
Before adding `kano` to the group, check if the user exists. If not, create the user.

use `sudo cat /etc/passwd | grep kano` to check the user existance
use `sudo useradd kano` to create the user

### 3. Add User to Group:
Now, add the user `kano` to the `nautilus_admin_users` group.

`sudo usermod -aG nautilus_admin_users kano`

check the creation of group & user with `sudo cat /etc/group`

---

now repeat this step in all app servers.
