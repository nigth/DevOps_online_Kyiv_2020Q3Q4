## Task 4.3
### Module 4. Networking Fundamental
___

Build a local network that consists of 1 router, 5 computers and 2 servers. Saved project as `max-4-3.pkt`  

**4.3.1.** Put all components on the scheme, connected nodes.  
The Router and a Server-1 are connected by cross-over cable.  
Set "TRUNK" mode for one of switch's port, that connected to a router.  
![ScrShot 01](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m4/task4.3/shots/01.png "ScrShot 01")  

**4.3.2.** Assigned IP addresses (mask is everything `255.255.255.0`):  

| Host | IP |Gateway|
|:----:|:--:|:-----:|
|Srv0|192.168.0.1|192.168.0.100|
|PC1|192.168.0.11|192.168.0.100|
|PC2|192.168.0.12|192.168.0.100|
|PC3|192.168.0.13|192.168.0.100|
|PC4|192.168.0.14|192.168.0.100|
|PC5|192.168.0.15|192.168.0.100|
|Srv1|192.168.1.1|192.168.1.100|

![ScrShot 02](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m4/task4.3/shots/02.png "ScrShot 02")  

**4.3.3.** Assigned IPs `192.168.0.100` and `192.168.1.100` for the router.  
![ScrShot 03](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m4/task4.3/shots/03.png "ScrShot 03")  

**4.3.4.** Set password `iS3f5` on the router using command **`enable secret`**. 
```
Router2>enable
Router2#conf t
Router2(config)#enable secret 0 iS3f5
Router2(config)#exit
Router2#write
Router2#copy running-config startup-config
```
![ScrShot 04](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m4/task4.3/shots/04.png "ScrShot 04")  

**4.3.5.** Provided RIP settings on the router with networks `192.168.0.1` and `192.168.1.1`.  

![ScrShot 05](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m4/task4.3/shots/05.png "ScrShot 05")  

**4.3.6.** Checked connection with computers and servers, usnig simple PDU.  
![ScrShot 06](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m4/task4.3/shots/06.png "ScrShot 06")  
___

_Thanks for your time!_  





