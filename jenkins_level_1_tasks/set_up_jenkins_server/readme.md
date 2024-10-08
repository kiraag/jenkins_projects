# Jenkins Setup for CI/CD Pipelines - xFusionCorp Industries

## Task Summary

The DevOps team at **xFusionCorp Industries** is setting up CI/CD pipelines using Jenkins as the server. The following are the task requirements:

### Requirements:

1. **Install Jenkins** on the Jenkins server using the `yum` utility.
2. **Start the Jenkins service.**
   - Note: If you face a timeout issue while starting the Jenkins service, refer to the following [link](https://support.cloudbees.com/hc/en-us/articles/217078498-Troubleshooting-Jenkins-slowness-or-hanging-due-to-network-issues) for help.

3. **Create Jenkins admin user** with the following details:
   - Username: `<username>`
   - Password: `<password>`
   - Full Name: `<fullname>`
   - Email: `<mail_id>`

### Notes:
1. Access the Jenkins server by **SSH** using the root user and the provided password `S3curePass` from the **jump host**.
2. After Jenkins installation, access the Jenkins UI by clicking the **Jenkins button** on the top bar and follow the on-screen instructions to create the admin user.

---

## Steps to execute


# Jenkins Installation and Setup Guide

## 1. Access the Jenkins Server

SSH into the Jenkins server from the jump host using the root user:

```bash
ssh root@<Jenkins-Server-IP>
```

Use the provided password: `<provided_password>`.

---

## 2. Install Jenkins using Yum

### a. Install the necessary dependencies for Jenkins:

```bash
yum install java-11-openjdk-devel -y
```

### b. Add the Jenkins repository:

```bash
wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo
rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key
```

### c. Install Jenkins:

```bash
yum install jenkins -y
```

---

## 3. Start Jenkins Service

### a. Start Jenkins:

```bash
systemctl start jenkins
```

### b. Enable Jenkins to start on boot:

```bash
systemctl enable jenkins
```

> **Note**: If you face timeout issues while starting Jenkins, refer to the following link for help on common solutions: [Jenkins Timeout Issues](http://jenkins.io).

---

## 4. Set Up Jenkins Admin User

- Access the Jenkins UI by opening a web browser and navigating to:

  ```
  http://<Jenkins-Server-IP>:8080
  ```

- On the setup screen, you'll be asked to enter the initial admin password. Retrieve it using the following command:

  ```bash
  cat /var/lib/jenkins/secrets/initialAdminPassword
  ```

- Follow the on-screen instructions to create an admin user with the following details:

    - **Username**: `<given_username>`
    - **Password**: `<given_password>`
    - **Full Name**: `<given_full_name>`
    - **Email**: `<given_maid_id>`

---

## 5. Final Steps

- Complete the installation by selecting default plugins or choosing specific plugins as per your needs.
- After setup, click on the **Jenkins** button on the top bar to confirm that Jenkins is up and running successfully.

---

This should complete the Jenkins installation and setup.

