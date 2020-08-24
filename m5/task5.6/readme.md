## Task 5.6.
### Module 5. Linux

_In this task I work with Ubuntu 20 server_  

**The most task**: to allow user `utest` visit `guest`'s home directory.  
**The average task:** to acquaint with the basics of ACL and verify that ACL privileges override the chmod ones.  
```
sudo groupadd guest
sudo useradd -g guest -s /bin/bash -d /home/guest -m guest
sudo passwd guest
id guest
ls -ld /home/guest
id utest
```
![ScrShot 01](scr/01.png "ScrShot 01")  

**5.6.1.** .  
```
# find the partition with /home :
df -h
# home is on the /dev/sda5
mount -o remount -o acl /dev/sda5
tune2fs -l /dev/sda5
```
![ScrShot 02](scr/02.png "ScrShot 02")  

For the view UUID of disks, use `blkid` command from `guest` and with super privileges `sudo...`.  
As we can see, with  super privileges the UUID of `/dev/sda1` is displayed. From the `guest` - no:  
```
su guest
whoami
blkid
exit
sudo blkid
```
![ScrShot 03](scr/03.png "ScrShot 03")  

**5.6.2.** Log in as `guest`. Create in `/tmp` a directory called `acl_test`.  
By means of `chmod`, allow  `utest` to perform all possible operations (rwx) with respect to `acl_test`.  
```
su guest
whoami
mkdir /tmp/acl_test && cd "$_"
ls -ld /tmp/acl_test
ls -l /tmp/acl_test
chmod 777 /tmp/acl_test
getfacl /tmp/acl_test
exit
```
Verify that user `utest` is indeed capable of implementing granted him privileges.  
For example, after logging in as `utest`, create a file in `/tmp/acl_test` - `utest.txt` by `touch`.  
```
su utest
whoami
cd /tmp/acl_test
touch utest.txt
getfacl /tmp/acl_test/utest.txt
exit
```
![ScrShot 04](scr/04.png "ScrShot 04")  

**5.6.3.** Employ ACL to block any activity except reading, for `utest` with dir `/tmp/acl_test` _(hint: `setfacl`)_.  
```
su guest
whoami
setfacl -m u:utest:r /tmp/acl_test
getfacl /tmp/acl_test
exit
```
Test if the actions are effectively prohibited  
```
su utest
whoami
cd /tmp/acl_test
touch /tmp/acl_test/prohibited.txt
```
It is impossible to invoke this command, because `utest` has only READ permission.  
```
echo “new content” > /tmp/acl_test/utest.txt
```
Instead of that user `utest` is the owner of the file `/tmp/acl_test/utest.txt`,  
the `utest` is prevented from modifying content of the file `utest.txt` by means of ACL.  

![ScrShot 05](scr/05.png "ScrShot 05")  

**5.6.4.** Consider a situation when at the ACL level user `utest` is allowed to have all possible privileges  
with respect to `/tmp/acl_test`, while no action is allowed with chmod (conventional mechanism).  
_(Hint: repeat step 3, but given the new context)_.  
```
su guest
whoami
chmod 0 /tmp/acl_test
getfacl /tmp/acl_test
setfacl -m u:utest:rwx /tmp/acl_test
getfacl /tmp/acl_test
exit
```
![ScrShot 06](scr/06.png "ScrShot 06")  

Verify that user `utest` has permissions:  
```
su utest
whoami
cd /tmp/acl_test
getfacl /tmp/acl_test
getfacl /tmp/acl_test/utest.txt
touch /tmp/acl_test/prohibited.txt
echo “new content” > /tmp/acl_test/utest.txt
ls -ld /tmp/acl_test
exit
```
![ScrShot 07](scr/06.png "ScrShot 07")  

**5.6.5.** For user `utest`, set default ACLs to the directory `/tmp/acl_test` which allow read-only access  
_(hint: use the -d option of the setfacl command)_.  
```
su quest
whoami
getfacl /tmp/acl_test
setfacl -d -m u:utest:r /tmp/acl_test
getfacl /tmp/acl_test
exit
```
![ScrShot 08](scr/08.png "ScrShot 08")  

Being logged in as `utest`, invoke `touch` to create the file `utest2.txt` in the `/tmp/acl_test` directory.  
Query permissions on this file using `getfacl`.  
```
su utest
whoami
cd /tmp/acl_test
touch /tmp/acl_test/utest2.txt
echo “new content 2” > /tmp/acl_test/utest2.txt
getfacl /tmp/acl_test
getfacl /tmp/acl_test/utest2.txt
exit
```
So, the `utest` user can create a new file, but can't modify it.  
![ScrShot 09](scr/09.png "ScrShot 09")  

**5.6.6.** Set maximum permissions mask on `/tmp/acl_test/utest.txt` file  
in such a way as to allow read-only access. Check permissions with `getfacl`.  
```
su utest
whoami
getfacl /tmp/acl_test/utest.txt
chmod 100 /tmp/acl_test/utest.txt
chmod ug=r,o=r /tmp/acl_test/utest.txt
getfacl /tmp/acl_test/utest.txt
exit
```
![ScrShot 10](scr/10.png "ScrShot 10")  

**5.6.7.** Delete all ACL entries relative to the `/tmp/acl_test` directory.  
```
su guest
whoami
getfacl /tmp/acl_test
setfacl -bn /tmp/acl_test
getfacl /tmp/acl_test
exit
```
![ScrShot 11](scr/11.png "ScrShot 11")  

___
 
_Thanks for your time!_  
 


