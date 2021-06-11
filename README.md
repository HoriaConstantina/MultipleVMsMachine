## Instructions on how to run the machine

- First thing check if the VM's are running by typing vagrant status

- If the VM's are not running please do the following:
	- vagrant up (wait for the machines to be installed)
	- after the machines have been installed do vagrant ssh web
	- now you should have a Linux terminal
	- please do the following:
		- sudo nano .bashrc (at the bottom of the file type: export DB_HOST="mongodb://192.160.10.150:27017/posts")
		- source .bashrc
		- sudo nano /etc/profile (at the bottom of the file type: DB_HOST="mongodb://192.160.10.150:27017/posts")
	
	- cd /home/ubuntu/app/seeds
	- node seed.js (wait for the terminal to tell you **Database Cleared, Database Seeded**
	- cd ..
	- node app.js
	- Open a browser and go to 192.160.10.110
