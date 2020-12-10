# ownCloud Quickstart Installation

**Welcome** to the ownCloud Server Quickstart Installation Guide. This guide provides an overview
of the administration tasks to install and configure ownCloud, which is an open source
synchronization and sharing application.  

ownCloud includes the ownCloud server, which runs on Linux, client applications for Microsoft
Windows, Mac OS X and Linux, and mobile clients for the Android and Apple iOS operating
systems.

## Installing ownCloud

Before you start the ownCloud installation, review the [deployment considerations](https://doc.owncloud.com/server/10.5/admin_manual/installation/deployment_considerations.html), [deployment
recommendations](https://doc.owncloud.com/server/10.5/admin_manual/installation/deployment_recommendations.html), and [system requirements](https://doc.owncloud.com/server/10.5/admin_manual/installation/system_requirements.html). 

There is more than one way to install ownCloud.

[Install with Docker](https://doc.owncloud.com/server/10.6/admin_manual/installation/docker/)
: ownCloud can be installed using Docker, with the official [ownCloud Docker image](https://hub.docker.com/r/owncloud/server/tags). This official image works standalone for a quick evaluation, but is designed to be used in a docker-compose setup.

[Install manually](https://doc.owncloud.com/server/10.6/admin_manual/installation/manual_installation.html)
: Manually install ownCloud on Linux.

[Install using command line](https://doc.owncloud.com/server/10.6/admin_manual/installation/command_line_installation.html)
: ownCloud can be installed entirely from the command line. This is convenient for scripted operations and for system administrators who prefer using the command line over a GUI.


## Enable users to connect to the ownCloud server

As an administrator, you can enable users to connect to the ownCloud server using the server IP
address and port 8080.

1. In the LDAP configuration panel, click the **Server** tab.
2. For **Server Configuration**, configure one or more LDAP servers.
3. For **Host**, enter the server's IP address.
4. For **Port**, enter *8080*.

## Add a user account

Configure user accounts on the **Users** page in ownCloud. The default view displays basic
information about your users.

For more detailed information on setting up user accounts, refer to [User Management](https://doc.owncloud.com/server/10.5/admin_manual/configuration/user/user_configuration.html).

1. In the **Users** default view, enter the user's login name.

    Login names must be unique and cannot be edited.

    Note: Login names can contain letters, numbers, dashes, underscores, periods and at symbols (@).

2. Enter the user's email address.

    The user will receive an email to set their password. The email address can be edited at any time.

3. (Optional) Assign **Groups** memberships from the drop-down.

    By default new users are not assigned to any groups.

4. Click **Create**.

## Connect to ownCloud server using a desktop client

The installation wizard takes you step-by-step through configuration options and account setup.

**Before you begin**
[Complete the installation of the desktop synchronization client.](https://doc.owncloud.com/desktop/installing.html)

1. In the **ownCloud Connection Wizard**, enter the URL of your ownCloud server and click **Next**.

2. Enter your ownCloud login credentials and click **Next**.

3. In **Setup local folder options**, select to sync all of your files on the ownCloud server, or select individual folders.

4. Click **Connect** to connect to the ownCloud server.