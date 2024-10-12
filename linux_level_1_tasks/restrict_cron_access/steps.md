In alignment with security compliance standards, the Nautilus project team has opted to impose restrictions on crontab access. Specifically, only designated users will be permitted to create or update cron jobs.

Configure crontab access on App Server 2 as follows: Allow crontab access to `yousuf` user while denying access to the `rod` user.

---

## To configure crontab access on App Server 2 in a way that allows the `yousuf` user while denying the `rod` user, you'll need to manage the files `/etc/cron.allow` and `/etc/cron.deny`. These files control which users can or cannot use crontab for scheduling cron jobs.

Here's how you can set it up:

## Step-by-Step Instructions:

### 1. Log in to App Server 2:

```bash
ssh your_username@app_server_2_IP
```
### 2. Create or Update the `/etc/cron.allow` File:

To explicitly allow `yousuf` user to access crontab, you need to add their username to the `/etc/cron.allow` file.
If the file doesn't exist, you can create it.

```bash
echo "yousuf" | sudo tee -a /etc/cron.allow
```

 - Explanation:

    - The `echo` "`yousuf`" outputs the string "`yousuf`".

    - `sudo tee -a /etc/cron.allow` appends the output to the file `/etc/cron.allow`.

This ensures that only users listed in `/etc/cron.allow` are permitted to use crontab.

### 3. Create or Update the `/etc/cron.deny` File:

To deny rod access to crontab, add the `rod` user to `/etc/cron.deny`.
If the file doesn’t exist, you can create it.

```bash
echo "rod" | sudo tee -a /etc/cron.deny
```

 - Explanation:

    This adds `rod` to the list of users who are explicitly denied crontab access.

    The `/etc/cron.deny` file contains the names of users who are not allowed to use crontab.

### 4. Verify the Configuration:

You can verify the changes by checking the contents of both files:

```bash
cat /etc/cron.allow
cat /etc/cron.deny
```

You should see yousuf in `/etc/cron.allow` and rod in `/etc/cron.deny`.

### Important Notes:

 - If both `/etc/cron.allow` and `/etc/cron.deny` exist, only the allow file is considered, and only users listed in `/etc/cron.allow` can use crontab. In that case, `rod` won’t need to be in `/etc/cron.deny` because they won't be listed in `/etc/cron.allow`.

This setup should comply with the security standard by allowing `yousuf` and denying `rod` from managing cron jobs.