Following a security audit, the xFusionCorp Industries security team has opted to enhance application and server security with `SELinux`. To initiate testing, the following requirements have been established for `App server 1` in the Stratos Datacenter:

Install the required `SELinux packages`.

Permanently `disable SELinux` for the time being; it will be re-enabled after necessary configuration changes.

No need to `reboot` the server, as a scheduled maintenance reboot is already planned for tonight.

Disregard the current status of SELinux via the command line; the final status after the reboot should be disabled.
---

## To install the required `SELinux packages` and p`ermanently disable SELinux on App server 1` in the Stratos Datacenter, follow these steps:

## 1. Access App server 1:

Log in via SSH.

```bash
ssh username@server-ip
```

## 2. Install `SELinux packages`: 

Use the `package manager` to install `SELinux-related packages`. For example, on a CentOS/RHEL system, you can use:

```bash
sudo yum install -y selinux-policy-targeted policycoreutils
```

For Ubuntu or Debian-based systems, you can use:

```bash
sudo apt install -y selinux-basics selinux-policy-default
```

### 3. Disable SELinux permanently: 

Open the SELinux configuration file in a text editor:

```bash
sudo vi /etc/selinux/config
```

Find the line that reads:

```bash
SELINUX=enforcing
```

Change it to:

```bash
SELINUX=disabled
```

Save and exit

### 4. Verify current status (optional): 

Although we mentioned to disregard the current status, but we can check it using:

```bash
sestatus
```

However, we need to confirm that it will be disabled after the reboot.

- No need to reboot now: Since a scheduled maintenance reboot is planned for tonight, there's no need to reboot the server immediately.

- After the scheduled reboot, SELinux will be disabled as per your requirements.






