# Contents
{:.no_toc}

* Will be replaced with the ToC, excluding the "Contents" header
{:toc}

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

### Installing with Docker

Install ownCloud using Docker with the official [ownCloud Docker image](https://hub.docker.com/r/owncloud/server/tags).

**Before you begin**

The following instructions are for local installation. For remote access, the value of
OWNCLOUD_DOMAIN must be adapted.

`docker run -e OWNCLOUD_DOMAIN=localhost:8080 -p8080:8080 owncloud/server`

The Docker Compose configuration does the following:

* Exposes ports 8080, allowing for HTTP connections.
* Uses separate MariaDB and Redis containers.
* Mounts the data and MySQL data directories on the host for persistent storage.

1. Create a new project directory.

2. Copy and past the sample `docker-compose.yml` into the new project directory.

3. Create a `.env` configuration file, which contains the required configuration settings.

|Required Setting |Description |Example|
|---|---|---|
|OWNCLOUD_VERSION |The ownCloud version |latest |
|OWNCLOUD_DOMAIN |The ownCloud domain |localhost:8080|
|ADMIN_USERNAME |The admin username |admin|
|ADMIN_PASSWORD |The admin user’s password |admin|
|HTTP_PORT |The HTTP port to bind to |8080|

4. Start the container using your preferred Docker command-line tool.

5. When the process completes, run docker-compose ps to verify that all containers started successfully.

    **Important**: All files stored in this setup are contained in Docker
volumes, rather than a physical filesystem tree. It is the admin’s
responsibility to persist the files. Use, e.g., `docker volume ls |
grep ownclouddockerserver to inspect the volumes. Use e.g.,
docker run -v ownclouddockerserver_files:/mnt ubuntu
tar cf - -C /mnt . > files.tar` to export the files as a tar
archive.
Although all important data persists after `docker-compose down;
docker-compose up -d`, there are certain details that get lost, e.g.,
default apps may re-appear after they were uninstalled.

**What to do next**
Although the containers are up and running, it might still take a few minutes until ownCloud is fully
functional. Run, e.g., `docker-compose logs --follow owncloud` and inspect the log output.
Wait until the output shows **Starting apache daemon…** before you access the web UI.
To log in to the ownCloud UI, open http://localhost:8080 in your browser of choice. The username
and password are the admin username and password which you stored in `.env` earlier.



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

Results

When the connection is successful, two options are displayed:

* Connect to your ownCloud Web GUI
* Open your local folder

The server will also start synchronizing your files.

## Connect to the ownCloud server using a mobile client

You can connect to the ownCloud server using the web interface on any mobile device operating
system without installing the client software. You also can download the ownCloud app for additional
features.

To download the app on any iOS or Android device, open a web browser and access your ownCloud
server. Log in and access your **Personal** page to locate a link to the ownCloud app in iTunes or
the Google Play Store. When you download and open the app, you will be prompted to log in
before the app opens your Files page.