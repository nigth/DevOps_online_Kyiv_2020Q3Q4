## Task 5.1
### Module 5. Linux Essentials

**1.** Set up Linux Virtual Machine in VirtualBox. *Use Centos 8.2 Core x86_64 minimal.*  
![ScrShot 01](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m5/task5.1/scr/01.png "ScrShot 01")  

**2.** Try commands and utilities.  
- switching between virtual terminals (consoles).  
_Use for this action next shortcuts: [Alt]+[F1]...[Alt]+[F6]_   
- Print the values of the environment VARIABLEs. If no VARIABLE, print name and value pairs for them all.  
```
printenv
``` 
![ScrShot 02](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m5/task5.1/scr/02.png "ScrShot 02")  

- content of `/etc/profile` and `~/.bash_profile`  
```
cat /etc/profile
cat ~/.bash_profile
```
![ScrShot 03](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m5/task5.1/scr/03.png "ScrShot 03")  

- Show the file name from history is initialized and the number of commands to save in a history file.   
```
echo $HISTFILE
echo $HISTSIZE
echo $HISTFILESIZE
echo $HISTFILE $HISTSIZE $HISTFILESIZE
```
![ScrShot 04](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m5/task5.1/scr/04.png "ScrShot 04")  

- Get the information about logged users name with additional data.  
```
w
id
who
whoami
```
![ScrShot 05](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m5/task5.1/scr/05.png "ScrShot 05")  
___
 
_Thanks for your time!_  
