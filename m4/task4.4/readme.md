## Task 4.4 _(optional)_
### Module 4. Networking Fundamental
___
:heavy_check_mark: **4.4.1.** I have already deployed a network with 2 routers.  
Please see my previous task **4.2.1** _(here project name is `max-4-4-1.pkt`)_.  
https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/tree/master/m4/task4.2  
It works well, for example try a simple PDU modeling between all subnetworks - successful:  
![ScrShot 01](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m4/task4.4/shots/01.png "ScrShot 01")  
___
:white_check_mark: **4.4.2.** Organized 2 subnetworks with DHCP and DNS on the servers. Saved project as `max-4-4-2.pkt`  
![ScrShot 02](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m4/task4.4/shots/02.png "ScrShot 02")  

Assigned IP addresses (mask is everything `255.255.255.0`).  
Used "Trunk" mode for connections between switches and router.  
Assigned GW IP addresses on the router (192.168.1.1 and 192.168.2.1).  

| Host | IP |Gateway|
|:----:|:--:|:-----:|
|Srv1|192.168.1.11|192.168.1.1|
|PC1|192.168.1.12|192.168.1.1|
|PC2|192.168.1.13|192.168.1.1|
| | | |
|Srv2|192.168.2.11|192.168.2.1|
|PC3|192.168.2.12|192.168.2.1|
|PC4|192.168.2.13|192.168.2.1|

Checked that all connections are working well, used simple PDU modeling (with a static assigned IPs):  
![ScrShot 03](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m4/task4.4/shots/03.png "ScrShot 03")  

Let's go try to set up DHCP on both servers.  
![ScrShot 04](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m4/task4.4/shots/04.png "ScrShot 04")  

Checked that for example PC1 get a DHCP address and DNS address automatically - OK:  
![ScrShot 05](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m4/task4.4/shots/05.png "ScrShot 05")  

Checked that all connections are working well, used simple PDU modeling (this is with DHPC enabled):  
![ScrShot 05](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m4/task4.4/shots/05.png "ScrShot 05")  
___

_Thanks for your time!_  





