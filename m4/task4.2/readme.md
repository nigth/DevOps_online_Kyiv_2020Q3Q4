## Task 4.2
### Module 4. Networking Fundamentals

**1.** Created a model of enterprise network.  
There are 2 buildings with 2 floors. Each of workgroups on the floor has 5 computers.  
Because we have many hosts, we should better to use DHCP. Saved project as `max-4-2-1.pkt`  

**Office A** _(Router-A)_  
Floor A1: 192.168.11.0/24  
Floor A2: 192.168.12.0/24  
- **Floor A1** _(Switch-A1)_  
Net: 192.168.11.0/24  
Gateway: 192.168.11.1  
- **Floor A2** _(Switch-A2)_  
Net: 192.168.12.0/24  
Gateway: 192.168.12.1  

**Office B** _(Router-B)_  
Floor B1: 192.168.21.0/24  
Floor B2: 192.168.22.0/24  
- **Floor B1** _(Switch-B1)_  
Net: 192.168.21.0/24  
Gateway: 192.168.21.1  
- **Floor B2** _(Switch-B2)_  
Net: 192.168.22.0/24  
Gateway: 192.168.22.1  

**RIP** table on both Router-A and Router-B:  
192.168.11.0  
192.168.12.0  
192.168.21.0  
192.168.22.0  
192.168.30.0  
**Fiber channel** between offices on Router-A (192.168.30.1) and Router-B (192.168.30.2) interfaces.  

![ScrShot 01](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m4/task4.2/shots/01.png "ScrShot 01")  

**2.** Created a model of enterprise network. There is 1 building with 4 floors. On the each floors the are 2 workgroups with 3 and five computers respectively. Saved project as `max-4-2-2.pkt`  

![ScrShot 02](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m4/task4.2/shots/02.png "ScrShot 02")  

**3.** Created a model of enterprise network. There are 5 buildings with 1 floor. Each of buildings has 1 workgroup with 6 computers. The network is based on the 1-port router. Saved project as `max-4-2-3.pkt`  

![ScrShot 03](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m4/task4.2/shots/03.png "ScrShot 03")  

_Thanks for your time!_  


