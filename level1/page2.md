# Install ownCloud with command line

ownCloud can be installed entirely from the command line. This is convenient for scripted operations and for systems administrators who prefer using the command line over a GUI.
Ensure your server meets the ownCloud prerequisitesDownload and unpack the sourceInstall using the occ commandSet the correct owner and permissions
Download the Source Package (whether community or enterprise) directly from ownCloud, and then unpack (decompress) the tarball into the appropriate directory.Set your webserver user to be the owner of your unpacked owncloud directory.
$ sudo chown -R www-data:www-data /var/www/owncloud/
Use the occ command, from the root directory of the ownCloud source, to perform the installation.

Assuming you’ve unpacked the source to /var/www/owncloud/$ cd /var/www/owncloud/$ sudo -u www-data php occ maintenance:install \
   --database "mysql" --database-name "owncloud" \
   --database-user "root" --database-pass "password" \
   --admin-user "admin" --admin-pass "password"
You must run occ as your HTTP user. 
You do not need to run the Graphical Installation Wizard.
If you want to use a directory other than the default (which is data inside the root ownCloud directory), you can also supply the --data-dir switch. For example, if you were using the command above and you wanted the data directory to be /opt/owncloud/data, then add --data-dir /opt/owncloud/data to the command.
When the command completes, apply the correct permissions to your ownCloud files and directories.
 This is extremely important, as it helps protect your ownCloud installation and ensure that it will operate correctly. ext
