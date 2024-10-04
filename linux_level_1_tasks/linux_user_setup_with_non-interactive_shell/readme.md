# Task: Create a User with Non-Interactive Shell on App Server 2

To accommodate the backup agent tool's specifications, the system admin team at xFusionCorp Industries requires the creation of a user with a non-interactive shell. The following steps outline how to create a user named `john` with a non-interactive shell on **App Server 2**.

---

## Steps:

### 1. Log in to App Server 2 via SSH:
Use the following command to access **App Server 2**:

`ssh user@app-server-2`

### 2. Create the user john with a non-interactive shell

To create the user john and assign them a non-interactive shell (in this case, `/usr/sbin/nologin`), run:

`sudo useradd -s /usr/sbin/nologin john`

### 3. Verify the user creation
To ensure the user john was created successfully and assigned the non-interactive shell, check the /etc/passwd file:

`grep john /etc/passwd`

The output should look similar to this:

`john:x:1001:1001::/home/john:/usr/sbin/nologin`

This confirms that the user john has been successfully created with a non-interactive shell on App Server 2.
