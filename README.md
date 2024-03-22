# As I prepare to take the RHCSA I will work on practice questions and document them here.

---

- ### Add the following users: Arya, Jon, Rob, and Sansa
- #### ```useradd ``` arya
- ##### We will use the ```useradd``` command for each user

<details>
<summary></summary>

</details>

---
- ### Arya, Sansa, Jon and Rob should be members of a group called Starks
- #### ```groupadd``` Starks
- #### ```tail -1```/etc/group
- #### ```usermod``` Arya -G Starks

---
- ### Jon should also be a member of Snow
- #### ```groupadd``` Snow
- #### ```usermod``` Jon ```-aG``` Snow
- #### ```Id```Jon
---
- ### Set the following password for all users: matrix19
- #### ```echo```"matrix19" | passwd Jon ```-stdin```
---
- ### Force all users to change their password next time they login
- #### ```passwd``` ```-e``` Arya
- ##### we will do the same for Jon, Rob and Sansa
---
- ### Add a user called ramsay with the following UID 1250. Set the password: matrix19
- #### ```useradd``` ```-u``` 1250 ramsay
- #### ```echo``` "matrix19" | ```passwd``` ramsay ```--stdin```
---
- ### Add a user called little finger and lock his account
- #### ```useradd``` littlefinger
- #### ```usermod``` -L littlefinger
- #### ```tail -1``` /etc/shadow
---
- ### Create a shared directory called /Starksfamiily that belongs to the group Starks
- #### ```mkdir``` /Starksfamily
- #### ```chown``` :Starks /Starksfamily or ```chgrp``` Starks /Starksfamily
---
- ### Members of the Stark group should be able to read, write, & execute
- #### ```chmod``` g=rwx Starksfamily/
- #### ```ls -all``` | ```grep``` Starksfamily
---
- ### Please create a backup of the fstab to /var/tmp
- #### ```Cp``` /etc/fstab    /var/tmp
---
- ### Root should have full permissions over the /var/tmp/fstab file
- #### ```Cd``` /var/tmp
- #### ```ls -all```
- #### ```Chmod u=rwx``` /var/tmp/fstab
---
- ### Others should have no access over the /var/tmp/fstab file
- #### ```Chmod o= -``` /var/tmp/fstab
---
- ### Create a file in the /var/tmp directory called Winterfall
- #### ```touch``` /var/tmp/Winterfall 
---
- ### Group ownership for the file should be for the Starks group 
- #### ```chown``` :Starks Winterfall
---
### Schedule a wake-up message using logger: "Good Morning Sir"; for littlefinger to run every Wednesday at 7:55 a.m.
- #### ```Su``` - littlefinger
- #### ```crontab -e```
- #### 55 07 * * 3 logger "Good Morning, Sir"
---
### Create a group called developers 
- #### ```groupadd``` developers
---
### A user Dax and Max should belong to the "developers" group a secondary group. A user Turmund should have a non-interactive shell and shouldn't be a member of the "developers" group. The password for all users created should be "matrix19." 
- #### ```useradd``` Max
- #### ```usermod``` Max -aG developers 
- ##### Do the same for Dax
- #### ```useradd``` Turmund
- #### ```usermod -s``` /sbin/nologin Turmund OR ```useradd -s``` /sbin/nologin Turmund (use this to do it all at once) 
- #### ```echo``` "matrix19" | passwd Max ```--stdin``` 
- ##### Do the same for Dax
---
### Ensure that all future files created in the /Starksfamily will be owned by the Starks group
- #### ```Chmod g+s``` Starksfamily
- #### ```ls -ld``` Starksfamily
---
- ### Please create 10 empty files in the directory
- #### ```touch``` Starksfamily | file{1..10}
---
### Search for all the files that belong to the group Starks & change the permission to 700
- #### ```Find``` /Starksfamily | ```-group``` Starks
- #### ```Find``` /Starksfamily | ```-group``` Starks ```-type f```
- ####  ```Find``` /Starksfamily | ```-group``` Starks ```-type f``` ```-exec chmod 700 {}\;```
- #### ```ls -l``` /Starksfamily
---
### Please reduce the filesystem mounted at /mnt/blacksails to 400MB

---

### Create a backup file named /tmp/thursday.tar.gz, that contains the content of /etc using gzip compression

---

### Generate a tuning profile recommendation, & apply it. Ensure that the profile is persistent. 
### > In preparation for a custom application to be run on a non-standard port, 7676/TCP, create a Selinux port policy that grants apache access. 
  
---

### Configure autofs to follow as described below to automatically mount a remote user's home directory: 
- #### ifj.example.com(10.1.10.178) NFS export /admins/ to your system
- #### This file system contains the user20 preconfigured home directory
- #### users20's home directory is ifj.example.com:/admins/user20
- #### users20's home directory should automatically mount locally to /admins

---

### Install the 'httpd' package. Ensure that the service starts when the system is booted. Grant Selinux access to port 7111/TCP for the httpd service. The label to use should be 'http port t' 







