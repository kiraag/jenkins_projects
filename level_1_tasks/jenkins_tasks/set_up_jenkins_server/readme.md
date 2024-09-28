# Jenkins Setup for CI/CD Pipelines - xFusionCorp Industries

## Task Summary

The DevOps team at **xFusionCorp Industries** is setting up CI/CD pipelines using Jenkins as the server. The following are the task requirements:

### Requirements:

1. **Install Jenkins** on the Jenkins server using the `yum` utility.
2. **Start the Jenkins service.**
   - Note: If you face a timeout issue while starting the Jenkins service, refer to the following [link](https://support.cloudbees.com/hc/en-us/articles/217078498-Troubleshooting-Jenkins-slowness-or-hanging-due-to-network-issues) for help.

3. **Create Jenkins admin user** with the following details:
   - Username: `theadmin`
   - Password: `Adm!n321`
   - Full Name: `Mariyam`
   - Email: `mariyam@jenkins.stratos.xfusioncorp.com`

### Notes:
1. Access the Jenkins server by **SSH** using the root user and the provided password `S3curePass` from the **jump host**.
2. After Jenkins installation, access the Jenkins UI by clicking the **Jenkins button** on the top bar and follow the on-screen instructions to create the admin user.

---

## Steps to Execute

### 1. SSH into the Jenkins Server
SSH into the Jenkins server from the jump host using the following credentials:

```bash
ssh root@<Jenkins-Server-IP>

