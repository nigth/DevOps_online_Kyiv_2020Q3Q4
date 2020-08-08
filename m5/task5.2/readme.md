## Task 5.2
### Module 5. Linux

**1.** See my current working directory _(there should be my home directory)_.  
```
$pwd
/home/maxim
```
![ScrShot 01](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m5/task5.2/scr/01.png "ScrShot 01")  

**2.** Collect output of `ls` command with any parameters.  
- `ls -l /` shows detailed info about files in the ROOT directory (without hidden files).  
![ScrShot 02](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m5/task5.2/scr/02.png "ScrShot 02")  

- show info about files in the HOME directory (where we are now too):  
  - `ls` and `ls ~` are the same (if current directory is HOME = ~);
  - `ls -l` shows detailed info about files (without hidden);  
  - `ls -a` shows simple view of all files (including hidded);  
  - `ls -la` shows detailed info about all files (including hidden);  
  - `ls -lda ~` list home (~) directory themselve without content in detailed mode.  
![ScrShot 03](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m5/task5.2/scr/03.png "ScrShot 03")  
 
**3.** In this step we create a TEST folder, go to it, show current directory.  
Next we create an empty file TEST.TXT and list detailed information about him.  
Next create a new folder TEST2 and move file TEST.TXT there, go to this folder.  
Show list of files in the current TEST2 folder.  
Rename file TEST.TXT into TEST2.TXT and show list of files in the folder.  
Next we copy TEST2.TXT file into parent folder (..) - TEST, and go up (..).  
Show list of files and folders here, and delete the TEST2.TXT file.  
Finally we try to delete TEST2 folder, but get an error message (folder not empty).  
Because a TEST2.TXT file stay there. We can use flag `--ignore-fail-on-non-empty`.  
But for delete TEST2 folder, we shuld go into it, and delete all files inside at first.  
```
mkdir test
cd test
pwd
touch test.txt
ls -l test.txt
mkdir test2
mv test.txt test2
cd test2
ls
mv test.txt test2.txt
ls
cp test2.txt ..
cd ..
ls
rm test2.txt
rmdir test2
```
![ScrShot 04](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m5/task5.2/scr/04.png "ScrShot 04")  

**4.** All next command are using to show a contents of `/etc/fstab` file. The differences are next:  
- The **cat** command is the simplest way to view the contents of a file.  
- The **more** command displays the contents of the file one screen at a time for large files.  
- The **less** command is similar to the more command but provides extensive features. One important one is that it allows backward as well as forward movement in the file, even with pipes. Unlike **more**, if the file content fits the screen, less will still display the prompt.  
In our case, it doesn't matter because a `/etc/fstab` file is little, only for one page.  
```
cat /etc/fstab
more /etc/fstab
```
![ScrShot 05](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m5/task5.2/scr/05.png "ScrShot 05")  

```
less /etc/fstab
```
![ScrShot 06](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m5/task5.2/scr/06.png "ScrShot 06")  
**5.** Look through man pages of the listed above commands.  
```
man ls
man mkdir
man cd
man pwd
man touch
man mv
man rm
man rmdir
man cat
man less
man more
```
![ScrShot 07](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m5/task5.2/scr/07.png "ScrShot 07")  
___
 
_Thanks for your time!_  
 

