## Task 5.4
### Module 5. Linux

**1. User management.** I have 2 users in my system: `ROOT` and `MAXIM`. Here the new users `GUEST` and `USER` will be created.  

**1.1.** Create the new users `guest` and `user`  

![Screenshot 01](screenshts/01.png "Screenshot 01")  

**1.2.** Log in to the system as `user` _(hint: use `su`)._  

![Screenshot 02](screenshots/02.png "Screenshot 02")  

**1.3.** Edit `/etc/passwd` to prevent user `user` from logging in to the system.  

![Screenshot 03](screenshots/03.png "Screenshot 03")  

**2. Content of /etc/passwd and /etc/group.**  

**2.1.** Look through `/etc/passwd` and `/etc/group` _(hint: use `less` or `cat`)._  

![Screenshot 04](screenshots/04.png "Screenshot 04")  

**2.2.** Get data from `/etc/passwd` and `/etc/group` about users: `root`, `guest`, `user`, `maxim` _(hint: filter by `grep`)._  

![Screenshot 05](screenshots/05.png "Screenshot 05")  

**2.3.** Parse `/etc/passwd` and `/etc/group` with `cut`.  

![Screenshot 06](screenshots/06.png "Screenshot 06")  

**2.4.** Try to call `less` on `/etc/shadow` and invoke _(analyse content of `/etc/shadow` based on what was found in `man 5 shadow`):_  

![Screenshot 07](screenshots/07.png "Screenshot 07")  

**3. Dealing with chmod.** 

**3.1.** An executable script.  

![Screenshot 08](screenshots/08.png "Screenshot 08")  

**3.2.** Login in to the system as `guest`. Create directory `testDir` in the `/tmp`; put some file into `testDir` and prohibit user `user` from visitng this directory (i.e. `testDir`).  

![Screenshot 09](screenshots/07.png "Screenshot 09")  

**3.3** Test, if it possible to forbid an owner of some file to read to or write from this file.  

![Screenshot 10](screenshots/07.png "Screenshot 10")  

___
 
_Thanks for your time!_  
 

