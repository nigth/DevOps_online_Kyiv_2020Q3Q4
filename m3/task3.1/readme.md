## Task 3.1
### Module 3 Database Administration

**3.1.1.** Download MySQL server for your OS.  

I have installed MySQL DB on the remote server `SVT1111X1RS` (192.168.6.12).  
I work on the local machine `HP4330` (192.168.6.11). Both have local users `maxim`.  

The remote `root` MySQL login is restricted. Allowed only local `root` MySQL login.  
So lets go connect SSH to the DB server, check the version, and connect MySQL there:  
```
# local machine, HP4330 (192.168.6.11):
uname -a
hostname
whoami

ssh maxim@192.168.6.12
# remote server, SVT1111X1RS (192.168.6.12):
uname -a
hostname
whoami

mysql --version
mysql -p -u root
SELECT version ();
```
![ScrShot 01](scr/01.png "ScrShot 01")  

**3.1.2.** Install MySQL server.  

I have installed MySQL DB on the remote server `SVT1111X1RS` (192.168.6.12).  
I work on the local machine `HP4330` (192.168.6.11). Both have local users `maxim`.  

The MySQL server has an `amdin` DB user, who is allowed to connect MySQL remotely.  
So lets go remote connect the DB server with MySQL `amdin` user, check the version:  
```
# local machine, HP4330 (192.168.6.11):
uname -a
hostname
whoami

mysql -h 192.168.6.12 -p -u amdin
# remote server, SVT1111X1RS (192.168.6.12):

SELECT version();
```
![ScrShot 02](scr/02.png "ScrShot 02")  

- _**Pay attention,** on the next steps I use remote connection to the MySQL with `amdin` credentials._  

**3.1.3.** Describe the database schema (minimum 3 tables).  

The office is divided into departments that have names and are located in different cities.  
For each office employee there first and last name, date of employment, position, monthly rate.  
Each employee belongs to only one department.  
Each employee has only one boss. The president of the office does not have a boss.  
If the employee works as a salesman, he receives an additional compensation at the end of year.  
Each employee belongs to a group depending on his salary.  
For each group, the lower and upper limit of salary is determined.  

![ScrShot 03](scr/03.png "ScrShot 03")  

**3.1.4.** Create a database on the server through the console.  
```
# Create a database named `OFFICE` and switch to it.
CREATE DATABASE OFFICE;
USE OFFICE;

# Create a table 1 named DEPARTMENT, which has the ID field of integer type, 
# and NAME and CITY fields of string type with the length limited by 30 characters.
CREATE TABLE DEPARTMENT (ID INT, NAME VARCHAR(30), CITY VARCHAR(30));

# Create a table 2 named EMPLOYEE with the following fields: 
#ID (key field), FIRSTNAME, LASTNAME, POSITION – string type, 
#DATE_EMPLOYMENT – date type, ID_DEPARTMENT, ID_BOSS, RATE, BONUS – integer type.
CREATE TABLE EMPLOYEE (ID INT PRIMARY KEY,
FIRSTNAME VARCHAR(30),
LASTNAME VARCHAR(30),
POSITION VARCHAR(10),
DATE_EMPLOYMENT DATE,
ID_DEPARTMENT INT,
ID_BOSS INT,
RATE INT, 
BONUS INT);

# Create a table 3 named SALARY_GRADE with the following fields: ID (key field), 
#lower and upper salary bounds LOW_SALARY, HIGH_SALARY – integer type.
CREATE TABLE SALARY_GRADE (ID INT PRIMARY KEY, LOW_SALARY INT, HIGH_SALARY INT);

# Display what was created:
SHOW TABLES;
```
![ScrShot 04](scr/04.png "ScrShot 04")  

**3.1.5.** Fill in tables.  


![ScrShot 05](scr/05.png "ScrShot 05")  

![ScrShot 06](scr/06.png "ScrShot 06")  

![ScrShot 07](scr/07.png "ScrShot 07")  

**3.1.6.** Execute SQL queries DDL, DML, DCL.  

![ScrShot 08](scr/08.png "ScrShot 08")  

**3.1.7.** Create database users with different rights.  

![ScrShot 09](scr/09.png "ScrShot 09")  

**3.1.8.** Make a selection from the main table DB MySQL.  

![ScrShot 10.](scr/10.png "ScrShot 10")  
___
 
_Thanks for your time!_  
