## As part of the temporary assignment to the Nautilus project, a developer named rose requires access for a limited duration. To ensure smooth access management, a temporary user account with an expiry date is needed. Here's what you need to do: 

## Create a user named rose on App Server 3 in Stratos Datacenter. Set the expiry date to 2024-01-28, ensuring the user is created in lowercase as per standard protocol.

---

# Task

## To create a user named `rose` on `App Server 3` in the Stratos Datacenter with an `expiry date` of `2024-01-28`, you can follow these steps in a Linux environment:

### 1. Access App Server 3:
First, log into App Server 3. You can use SSH for this:

`ssh username@app-server-3-ip`

Replace username with your actual username and app-server-3-ip with the IP address or hostname of App Server 3.

### 2. Create the User `rose`:
Once you are logged into the server, you can create the user using the `useradd` command:

`sudo useradd -e 2024-01-28 rose`

`-e 2024-01-28`: This flag sets the account's expiration date to January 28, 2024.
`rose`: The username in lowercase.

### 3. Set the Password for the User:
You can set a password for the user after creating the account:
`sudo passwd rose`

### 4. Verify the User Creation and Expiry:
To verify that the user has been created with the correct expiry date, run:

`sudo chage -l rose`

This will show you the account details, including the expiry date.
