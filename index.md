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

<dl>
<dt>Install with Docker</dt>
<dd>ownCloud can be installed using Docker, with the official ownCloud Docker image. This official
image works standalone for a quick evaluation, but is designed to be used in a docker-compose
setup.</dd>
<dt>Install manually<dt>
<dd>Manually install ownCloud on Linux.</dd>
<dt>Install using command line</dt>
<dd>ownCloud can be installed entirely from the command line. This is convenient for scripted
operations and for system administrators who prefer using the command line over a GUI.</dd>


### Installing with Docker

Install ownCloud using Docket with the offical [ownCloud Docker image](https://hub.docker.com/r/owncloud/server/tags).

**Before you begin**
The following instructions are for local installation. For remote access, the value of
OWNCLOUD_DOMAIN must be adapted.
    docker run -e OWNCLOUD_DOMAIN=localhost:8080 -p8080:8080
owncloud/server
