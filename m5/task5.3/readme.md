## Task 5.3
### Module 5. Linux

**1.** Discover files with active sticky bits, use the following command:  
```
sudo find / -perm /6000 -type f -exec ls -ld {} \;>setuid.txt
```
The meaning of parameters of the above find command are next:  
- `-perm` : 
- `-type` : 
- `-exec` : 
  - `ls -ld {} \;` : If you run `find` with `exec`, `{}` expands to the filename of each file or directory found with `find` (so that `ls` in your example gets every found filename as an argument - note that it calls `ls` or whatever other command you specify once for each file found). Semicolon `;` ends the command executed by `exec`. It needs to be escaped with `\` so that the shell you run `find` inside does not treat it as its own special character, but rather passes it to `find`.
  - `>setuid.txt` : provide output of the results into the `setuid.txt` file.  
![ScrShot 01](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m5/task5.3/scr/01.png "ScrShot 01")  

**2.** Discovering soft and hard links. In this step we create a TEST folder, go into it.  
Next create a TEST1.TXT file and put a line with his name inside, and show detailed list info.  
Next we create a file TEST2.TXT that is hard linked TEST1.TXT and on detailed list info see number of links - **2**.  
Next we put the name of file TEST2.TXT inside him, and delete first one TEST1.TXT and show detailed list info.  
After that we create a soft linked file TEST3.TXT, we can see information on the ls command output blue color.  
Finally we delete TEST2.TXT file, output ls information, and see that it was changed by red color.  
```
cd
mkdir test
cd test
touch test1.txt
echo "test1.txt" > test1.txt
ls -l . #(a hard link)

ln test1.txt test2.txt
ls -l . #(pay attention to the number of links to test1.txt and test2.txt)

echo "test2.txt" > test2.txt
cat test1.txt test2.txt
rm test1.txt
ls -l . #(now a soft link)

ln -s test2.txt test3.txt
ls -l . #(pay attention to the number of links to the created files)

rm test2.txt; ls -l .
```
![ScrShot 02](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m5/task5.3/scr/02.png "ScrShot 02")  

**3.** I/O redirect. Execute these commands; comment on the output.  
Firstly By command `blkid` we locate/print block device attributes, names, metadata, etc.  
Next by commands `mount` and `dmesg` we get info about mountpoint of `sda` device (disk), and info from Linux Kernel.  
Finally we redirect i/o flow  of GREP command into the `root_entries.txt` file, and show it's contents by `less`:  
```
mount
blkid
mount | grep sda
dmesg | grep sda
```
![ScrShot 03](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m5/task5.3/scr/03.png "ScrShot 03")  

```
sudo grep -R -e "root" /etc > root_entries.txt
less root_entries.txt
```
![ScrShot 04](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m5/task5.3/scr/04.png "ScrShot 04")  
___
 
_Thanks for your time!_  
 

