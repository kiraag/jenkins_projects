After conducting a security audit within the Stratos DC, the Nautilus security team discovered misconfigured permissions on critical files. To address this, corrective actions are being taken by the production support team. Specifically, the file named `/etc/hosts` on `Nautilus App 2 server` requires adjustments to its `Access Control Lists (ACLs)` as follows:

1. The file's `user owner` and `group owner` should be set to `root`.

2. Others should possess `read only` permissions on the file.

3. User `james` must not have any permissions on the file.

4. User `ryan` should be granted read only permission on the file.

---

## To address the required adjustments to the ACLs of the `/etc/hosts` file on the Nautilus App 2 server, you can follow these steps using `chown`, `chmod`, and `setfacl` commands:

### 1. Set the user and `group owner` of the file to root:

```bash
sudo chown root:root /etc/hosts
```
### 2. Set read-only permissions for others:

```bash
sudo chmod o=r /etc/hosts
```
This command ensures that others can only read the file without any write or execute permissions.

### 3. Deny all permissions to user `james`:

```bash
sudo setfacl -m u:james:0 /etc/hosts
```
This removes all permissions for the user `james` on the file.

### 4. Grant read-only permission to user `ryan`:

```bash
sudo setfacl -m u:ryan:r /etc/hosts
```
This command gives the user `ryan` read-only access to the file.

### Verify the Changes
To confirm the ACL settings, you can use the following command:

```bash
getfacl /etc/hosts
```

This will display the current ACLs for the `/etc/hosts` file, allowing you to verify that the permissions have been applied correctly.