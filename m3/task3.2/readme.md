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

The helpful post is here on the blog:  
https://www.1strategy.com/blog/2017/10/03/migrating-a-mysql-database-to-rds/

- Create the RDS instance:  
REGION - Europe (Frankfurt) eu-central-1;
Standard Create;  
Engine options - MySQL;  
Edition - MySQL community ver MySQL 5.7.30;  
Templates - Free Tier;  
Settings:  
DB instance identifier - office-2;  
Initial database name - OFFICE;  
![ScrShot 05](scr/05.png "ScrShot 05")  

Also create a Security Group for the VPC to restrict access from my IP address:  
![ScrShot 06](scr/06.png "ScrShot 06")  

Upload the `office_bckp.sql` file to the S3 bucket:  
![ScrShot 07](scr/07.png "ScrShot 07")  

- Log into the RDS MySQL instance and import the database by referencing the file saved from mysqldump  
```
mysql -u amdin -p -h office-2.ckyrbw0vxf0b.eu-central-1.rds.amazonaws.com  

show databases;
use OFFICE;
show tables;
source ~/office_bckp.sql;

show tables;
select * from DEPARTMENT;
select * from EMPLOYEE;

SELECT version ();
```

See that data restored successfully.  
The MySQL versions are different - on the AWS RDS - 5.7.30-log, on my host I have - 5.7.31-ubuntu (see task 3.1).  
![ScrShot 08](scr/08.png "ScrShot 08")  

![ScrShot 09](scr/09.png "ScrShot 09")  

![ScrShot 10.](scr/10.png "ScrShot 10")  

![ScrShot 11.](scr/11.png "ScrShot 11")  
___
 
_Thanks for your time!_  
