# Task
In response to the latest tool implementation at xFusionCorp Industries, the system admins require the creation of a service user account. Here are the specifics:

Create a user named `john` in App Server 3 without a home directory.

---

## To create a user named `john` without a home directory on App Server 3, follow these steps:

### 1. Login to App Server 3:
First, you'll need to log in to the App Server 3 using SSH or directly accessing the server.

`ssh user@appserver3`

### 2. Create the user without a home directory:
Use the `useradd` command with the `-M` option, which prevents the creation of a home directory for the user.

`sudo useradd -M john`

This will create a user named `john` without a home directory. You can verify the user creation with the following command:

`getent passwd john`

This will display the user entry from the `/etc/passwd` file, confirming the user has been added without a home directory.
