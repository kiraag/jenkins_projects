The Nautilus DevOps team has recently setup a Jenkins server, which they want to use for some CI/CD jobs. Before that they want to install some plugins which will be used in most of the jobs. Please find below more details about the task



1. Click on the `Jenkins button` on the top bar to access the Jenkins UI. Login using username `admin` and `Adm!n321` password.


2. Once logged in, install the `Git` and `GitLab` plugins. Note that you may need to restart Jenkins service to complete the plugins installation, If required, opt to Restart Jenkins when installation is complete and no jobs are running on plugin installation/update page i.e update centre.

---

## To install the `Git` and `GitLab` plugins on the Jenkins server, follow these steps:

### Steps to Install Jenkins Plugins

1. **Access Jenkins UI:**

    - Open the Jenkins server UI by clicking on the Jenkins button on the top bar.
    - Login using:
    - Username: <given_user_name>
    - Password: <given_password>

2. **Navigate to Plugin Management:**

    - After logging in, click on `Manage Jenkins` from the left-hand menu.
    - Under `System Configuration`, click on `Manage Plugins`.

3. **Install `Git` and `GitLab` Plugins:**

    - In the `Plugin Manager` window, go to the Available tab.
    - Search for the `Git` Plugin and `GitLab` Plugin in the search bar.
    - Select both plugins by checking the boxes next to their names.

4. **Install and Restart Jenkins:**

    - Click the Install without restart or Install and Restart Jenkins button at the bottom.
    - If a restart is required, select Restart Jenkins when installation is complete and no jobs are running.
    - Wait for Jenkins to restart and complete the plugin installation.

        **OPTIONAL**

        - If the plugins were failing to install, then check for updates of the previous dependencies and update all of them.
        - Now restart the jenkins and install the plugins.

---

Once completed, the plugins will be ready for use in your Jenkins jobs.



