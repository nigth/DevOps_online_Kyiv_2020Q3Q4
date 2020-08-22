## Task 5.5
### Module 5. Linux

__In this task I work with Ubuntu 20 server__

**1.** Create a new user `utest`.  
```
sudo groupadd utest
sudo useradd -g utest -s /bin/bash -d /home/utest -m utest
sudo passwd utest
id utest
ls -ld /home/utest
```
![ScrShot 01](scr/1.png "ScrShot 01")  

Add the `usrquota` option in the `/etc/fstab`  
```
sudo apt install quota
sudo vi /etc/fstab
sudo reboot now
```
![ScrShot 02](scr/2.png "ScrShot 02")

Based on the quota mechanism,  
```
sudo quotacheck -cu /home
ls -a /home
sudo quotacheck -vagum
```
![ScrShot 03](scr/3.png "ScrShot 03")  

limit the available disk space for `utest` to **soft**: 10M and **hard**: 15M. 
```
sudo edquta -u utest
sudo mount -o remount /home
```
![ScrShot 04](scr/4.png "ScrShot 04")  

**2.** Using MidnightCommander, copy content of `/usr` directory to `utest` home directory.  
```
sudo setquota -u utest 10M 15M 0 0 /home
sudo repquota /home
sudo edquota -t
su utest
whoami
mc
```
![ScrShot 05](scr/5.png "ScrShot 05")  

Copy files and get a quota warning:
![ScrShot 06](scr/6.png "ScrShot 06")  

And the report:  
```
sudo repquota /home
sudo repquota -s /home
```
![ScrShot 07](scr/7.png "ScrShot 07")  
___
 
_Thanks for your time!_  
 

