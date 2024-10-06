## Due to an accidental data mix-up, user data was unintentionally mingled on Nautilus App Server 3 at the /home/usersdata location by the Nautilus production support team in Stratos DC. To rectify this, specific user data needs to be filtered and relocated. Here are the details:

## Locate all files (excluding directories) owned by user kirsty within the /home/usersdata directory on App Server 3. Copy these files while preserving the directory structure to the /media directory.

---

## To locate and copy all files owned by user `kirsty` from `/home/usersdata` to the `/media` directory while preserving the directory structure on Nautilus App Server 3, you can follow these steps:

# Steps

### 1. Use the `find` command to locate the files: Run the `find` command to search for all files owned by `kirsty` in `/home/usersdata` and exclude directories:

`sudo find /home/usersdata -type f -user kirsty`

### 2. Copy the files while preserving the directory structure: Use the cp command with --parents to preserve the directory structure while copying the files:

`sudo find /home/usersdata -type f -user kirsty -exec cp --parents {} /media/ \;`

The command you've provided is used to find files owned by a specific user `(kirsty)` in the `/home/usersdata` directory and copy them to another location `(/media/)`, preserving their directory structure. Here’s a breakdown of the command:

`sudo`: Run the command with superuser privileges, allowing access to files that may require elevated permissions.

`find /home/usersdata`: Start searching in the `/home/usersdata` directory.

`-type f`: Specify that you're looking for files (not directories).

`-user kirsty`: Filter to find files owned by the user `kirsty`.

`-exec cp --parents {} /media/ \;`: For each file found, execute the `cp` command:

`cp`: The command to copy files.

`--parents`: This option preserves the directory structure of the source files when copying them to the destination. For example, if a file is found at `/home/usersdata/folder/file.txt`, it will be copied to `/media/home/usersdata/folder/file.txt`.

`{}`: A placeholder that represents the current file found by find.

`\;`: Indicates the end of the `-exec` command.

### Verifying:
After running the above commands, you can verify that the files have been copied correctly with the directory structure:
`ls -lR /media`

This command will display the files and directory structure under `/media` to ensure everything has been copied properly.















