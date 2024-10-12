In the daily standup, it was noted that the timezone settings across the Nautilus Application Servers in the Stratos Datacenter are inconsistent with the local datacenter's timezone, currently set to `Indian/Kerguelen`.

Synchronize the timezone settings to match the local datacenter's timezone (`Indian/Kerguelen`).

---

## To synchronize the timezone settings across the Nautilus Application Servers in the Stratos Datacenter to match the local datacenter's timezone (`Indian/Kerguelen`), follow these steps on each server:

## 1. Access each Nautilus Application Server: 

Log in via SSH 

```bash
ssh usename@server-ip
```

### 2. Check the current timezone:

You can check the current timezone with the following command:

```bash
timedatectl
```

### 3. Set the timezone:

Use the following command to set the timezone to `Indian/Kerguelen`:

```bash
sudo timedatectl set-timezone Indian/Kerguelen
```

### 4. Verify the change:

After setting the timezone, verify that it has been updated correctly:

```bash
timedatectl
```

### 5. Repeat on all servers:

Ensure you repeat these steps on each Nautilus Application Server in the Stratos Datacenter.

- These steps will ensure to set the timezone to `Indian/Kerguelen`

