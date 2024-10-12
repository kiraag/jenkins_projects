The Nautilus system admins team has rolled out a web UI application for their backup utility on the Nautilus backup server within the Stratos Datacenter. This application operates on `port 8089`, and `firewalld` is active on the server. To meet operational needs, the following requirements have been identified:

Allow all incoming connections on `port 8089/tcp`. Ensure the zone is set to `public`.
---

## To allow incoming connections on port 8089/tcp on the Nautilus backup server while ensuring the zone is set to public, follow these steps:

### 1. Access the Nautilus backup server: 

Log in via SSH

```bash
ssh user-name@server-ip
```

### 2. Check the active zone:

First, check which zone is currently active:

```bash
sudo firewall-cmd --get-active-zones
```

### 3. Set the zone to public (if it’s not already set):

If the active zone is not `public`, you can set it by using:

```bash
sudo firewall-cmd --set-default-zone=public
```

### 4. Allow incoming connections on `port 8089/tcp`:

```bash
sudo firewall-cmd --zone=public --add-port=8089/tcp  --permnent
```

### 5. Reload the firewall to apply changes:

```bash
sudo firewall-cmd --reload
```

### 6. Verify the rule:

Ensure the rule has been applied correctly:

```bash
sudo firewall-cmd --zone=public --list-ports
```

You should see `8089/tcp` in the list.

