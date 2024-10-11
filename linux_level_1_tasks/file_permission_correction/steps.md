After conducting a security audit within the Stratos DC, the Nautilus security team discovered misconfigured permissions on critical files. To address this, corrective actions are being taken by the production support team. Specifically, the file named /etc/hosts on Nautilus App 2 server requires adjustments to its Access Control Lists (ACLs) as follows:

1. The file's user owner and group owner should be set to root.

2. Others should possess read only permissions on the file.

3. User james must not have any permissions on the file.

4. User ryan should be granted read only permission on the file.

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