# borntoreboot

ssh fvaliyak@localhost -p 4242


Check that the UFW service: 	•	sudo ufw status

Check that the SSH service is started : 	•	sudo systemctl status ssh
									sudo service ssh status

Check that the chosen operating system is Debian or CentOS  : 	•	head -n 2 /etc/os-release


* The subject requests that a user with the login of the student being evaluated is present on the virtual machine. Check that it has been added and that it belongs to the “sudo” and “user42” groups.


    - groups <username>


* create a new user & Assign it to a password 



- sudo adduser <username>

- getent passwd <username>


* Password policy files

    - sudo vim /etc/login.defs
    - sudo vim /etc/pam.d/common-password

* create a group

- 		sudo addgroup evaluating
- 		adduser <username> evaluating

* Check that the hostname of the machine

- 		sudo hostnamectl status

* Modify this hostname
		sudo hostnamectl set-hostname <new-hostname>
		sudo vim /etc/hosts
		sudo reboot


* To view the partitions for this virtual machine

			lsblk

* Check that the “sudo” program is properly installed
    * sudo
    * dpkg -l | grep sudo
* The student being evaluated should now show assigning your new user to the “sudo” Group.
    * adduser <username> sudo
    * groups <username>


* Sudo policy file
    * sudo vim /etc/sudoers.d/sudo_config
* Verify that the “var/log/sudo” folder exists and has at least one file. Check the contents of the files in this folder, you should see a history of the commands used with sudo. Finally, try to run a command via sudo. See if the file(s) in the “var/log/sudo” folder has been updated.
    * sudo vim /var/log/sudo/sudo.log


* “UFW” program is properly installed on the virtual machine.
    * dpkg -l | grep ufw
* Check that it is working properly.
    * sudo ufw status
* Add a new rule to open port 8080. 
    * sudo ufw allow 8080
* Finally, delete this new rulesudo 
    * ufw delete <rule number>
    * sudo ufw delete allow <port number>


* Check that the SSH service is properly installed on the virtual machine
    * dpkg -l | grep ssh
* Check that it is working properly.
    * sudo systemctl status ssh
* Verify that the SSH service only uses port 4242.
    * sudo systemctl status ssh
    * ssh <user>@localhost -p 4242
    * ssh root@localhost -p 4242 should not work!



* How their script works by showing you the code.
    * sudo vim /usr/display_message/monitoring.sh

* How the student being evaluated set up their script so that it runs every 10 minutes from when the server starts
    * sudo crontab -u root -e
