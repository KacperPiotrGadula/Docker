#Instalation Dockle in ubuntu

https://github.com/goodwithtech/dockle/releases

1) Download the Correct File: Download the dockle_0.4.14_Linux-64bit.tar.gz file from the release page. You can use curl or wget, for example:

wget https://github.com/goodwithtech/dockle/releases/download/v0.4.14/dockle_0.4.14_Linux-64bit.tar.gz

2) Extract the Tarball: Once the file is downloaded, extract it:

tar -xvzf dockle_0.4.14_Linux-64bit.tar.gz

3) Move to /usr/local/bin: Make it executable and move it to a directory in your PATH:

chmod +x dockle
sudo mv dockle /usr/local/bin/dockle

4) Check the Version: Verify the installation by running:

dockle --version

5) Use dockle to check your image e.g.:

dell@DESKTOP-E9H427N:~$ dockle ubuntu
WARN    - CIS-DI-0001: Create a user for the container
        * Last user should not be root
WARN    - DKL-DI-0006: Avoid latest tag
        * Avoid 'latest' tag
INFO    - CIS-DI-0005: Enable Content trust for Docker
        * export DOCKER_CONTENT_TRUST=1 before docker pull/build
INFO    - CIS-DI-0006: Add HEALTHCHECK instruction to the container image
        * not found HEALTHCHECK statement
INFO    - CIS-DI-0008: Confirm safety of setuid/setgid files
        * setuid file: urwxr-xr-x usr/bin/su
        * setuid file: urwxr-xr-x usr/bin/mount
        * setgid file: grwxr-xr-x usr/sbin/pam_extrausers_chkpwd
        * setuid file: urwxr-xr-x usr/bin/umount
        * setuid file: urwxr-xr-x usr/bin/passwd
        * setuid file: urwxr-xr-x usr/bin/gpasswd
        * setgid file: grwxr-xr-x usr/sbin/unix_chkpwd
        * setuid file: urwxr-xr-x usr/bin/chfn
        * setuid file: urwxr-xr-x usr/bin/chsh
        * setgid file: grwxr-xr-x usr/bin/chage
        * setuid file: urwxr-xr-x usr/bin/newgrp
        * setgid file: grwxr-xr-x usr/bin/expiry

