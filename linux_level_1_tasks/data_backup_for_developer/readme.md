### Within the Stratos DC, the Nautilus storage server hosts a directory named `/data`, serving as a repository for various developers non-confidential data. Developer `ammar` has requested a copy of their data stored in `/data/ammar`. The System Admin team has provided the following steps to fulfill this request:

### a. Create a compressed archive named `ammar.tar.gz` of the `/data/ammar` directory.

### b. Transfer the archive to the /home directory on the Storage Server.

---

## To create a compressed archive of the `/data/ammar` directory and transfer it to the `/home` directory on the Nautilus storage server, follow these steps:

### Step 1: SSH into the Storage Server
Log into the Nautilus storage server as a user with appropriate permissions using SSH:

`ssh your_user@storage_server_ip`

Replace `your_user` with your username and `storage_server_ip` with the IP address of the storage server.

### Step 2: Create the Compressed Archive
Create a compressed archive of the /data/ammar directory using tar:

`sudo tar -czvf ammar.tar.gz /data/ammar`

Options explained:

`-c`: Creates a new archive.

`-z`: Compresses the archive using gzip.

`-v`: Displays the progress in the terminal.

`-f`: Specifies the filename of the archive (`ammar.tar.gz`)

This command will create a file named `ammar.tar.gz` in the current working directory.

### Step 3: Move the Archive to the `/home` Directory
Move the `ammar.tar.gz` file to the `/home` directory:

`sudo mv ammar.tar.gz /home`

### Step 4: Verify the Archive Transfer
Check if the file exists in the `/home` directory to ensure the transfer was successful:

`ls -lh /home/ammar.tar.gz`

This should list the `ammar.tar.gz` file in the `/home` directory with its size.

### Summary
-SSH into the storage server.

-Create a compressed archive of the `/data/ammar` directory.

-Move the archive to the `/home` directory.

-Verify the archive exists in the new location.

-These steps will fulfill the developer’s request to create and transfer a copy of their data.



