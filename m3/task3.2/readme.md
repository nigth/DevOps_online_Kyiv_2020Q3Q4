## Task 3.2
### Module 3 Database Administration

**3.2.1.** Make backup of your database.  
```
ssh maxim@192.168.6.12
sudo mysqldump OFFICE -u amdin -p > office_bckp.sql
ls -li office_bckp.sql
exit
```
![ScrShot 01](scr/01.png "ScrShot 01")  

**3.2.2.** Delete the table EMPLOYEES and all data from the column CITY of the DEPARTMENT table.  
```
mysql -h 192.168.6.12 -p -u amdin
USE OFFICE;
SHOW TABLES;

DROP TABLE EMPLOYEE;
ALTER TABLE DEPARTMENT DROP COLUMN CITY;

SHOW TABLES;
SELECT * FROM DEPARTMENT;
QUIT;
```
![ScrShot 02](scr/02.png "ScrShot 02")  

**3.2.3.** Restore your database.  
```
ssh maxim@192.168.6.12
ls -li office_bckp.sql
sudo mysql OFFICE -u amdin -p < office_bckp.sql
exit
```
![ScrShot 03](scr/03.png "ScrShot 03")  


Check the data restored:  
```
mysql -h 192.168.6.12 -p -u amdin
USE OFFICE;
SHOW TABLES;
SELECT * FROM EMPLOYEE;
SELECT * FROM DEPARTMENT;
```
![ScrShot 04](scr/04.png "ScrShot 04")  


**3.2.4.** Transfer your local database to RDS AWS.  

![ScrShot 05](scr/05.png "ScrShot 05")  





![ScrShot 06](scr/06.png "ScrShot 06")  

![ScrShot 07](scr/07.png "ScrShot 07")  

![ScrShot 08](scr/08.png "ScrShot 08")  

![ScrShot 09](scr/09.png "ScrShot 09")  

![ScrShot 10.](scr/10.png "ScrShot 10")  
___
 
_Thanks for your time!_  
