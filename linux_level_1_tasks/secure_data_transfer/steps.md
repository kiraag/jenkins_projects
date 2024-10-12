A Nautilus developer has stored confidential data on the jump host within Stratos DC. To ensure security and compliance, this data must be transferred to one of the app servers. Given developers lack direct access to these servers, the system admin team has been enlisted for assistance.

Copy `/tmp/nautilus.txt.gpg` file from jump server to App Server 3 placing it in the directory `/home/app`.

## To securely transfer the file `/tmp/nautilus.txt.gpg` from the jump server to App Server 3, we can use `scp (secure copy protocol)` since it allows copying files over SSH. Here's the step-by-step process:

### Step-by-Step Instructions

1. Access the Jump Server:

First, you'll need to log in to the jump server using SSH.

```bash
ssh <your_username@jump_server_IP>
```
2. Copy the File from the Jump Server to App Server 3:

 - Once you're logged in to the jump server, use the scp command to transfer the file. You'll need to know the IP or hostname of App Server 3 and have the appropriate SSH credentials.

```bash
scp /tmp/nautilus.txt.gpg your_username@app_server_3_IP:/home/app/
```
 - Explanation:
    - `scp`: Secure copy command.
    - `/tmp/nautilus.txt.gpg`: The file to copy.
    - `your_username@app_server_3_IP`: Your SSH username and the IP or hostname of App Server 3.
    - `/home/app/`: The destination directory on App Server 3 where the file will be placed.

3. Verify the File Transfer:

 - After the transfer completes, log in to App Server 3 to confirm that the file is in the `/home/app` directory.

 ```bash
 ssh your_username@app_server_3_IP
 ls /home/app/nautilus.txt.gpg
 ```
This command should list the file if the transfer was successful.

