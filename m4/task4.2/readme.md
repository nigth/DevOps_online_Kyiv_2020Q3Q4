## Task 4.2
### Module 4. Networking Fundamentals

**1.** Created a model of enterprise network. There are 2 buildings with 2 floors.  
Each of workgroups on the floor has 5 computers. Saved project as `max-4-2-1.pkt`  

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

**RIP** table on both Router-A and Router-B is the same, consists all our networks:  
192.168.11.0  
192.168.12.0  
192.168.21.0  
192.168.22.0  
192.168.30.0  
**Fiber channel** between offices on Router-A (192.168.30.1) and Router-B (192.168.30.2) interfaces.  

Assigned IP addresses for computers (mask is everything 255.255.255.0):

| Host | IP |Gateway|
|:----:|:--:|:-----:|
|PC-AF1-1|192.168.11.11|192.168.11.1|
|PC-AF1-2|192.168.11.12|192.168.11.1|
|PC-AF1-3|192.168.11.13|192.168.11.1|
|PC-AF1-4|192.168.11.14|192.168.11.1|
|PC-AF1-5|192.168.11.15|192.168.11.1|
| | | |
|PC-AF2-1|192.168.12.11|192.168.12.1|
|PC-AF2-2|192.168.12.12|192.168.12.1|
|PC-AF2-3|192.168.12.13|192.168.12.1|
|PC-AF2-4|192.168.12.14|192.168.12.1|
|PC-AF2-5|192.168.12.15|192.168.12.1|
| | | |
|PC-BF1-1|192.168.21.11|192.168.21.1|
|PC-BF1-2|192.168.21.12|192.168.21.1|
|PC-BF1-3|192.168.21.13|192.168.21.1|
|PC-BF1-4|192.168.21.14|192.168.21.1|
|PC-BF1-5|192.168.21.15|192.168.21.1|
| | | |
|PC-BF2-1|192.168.22.11|192.168.22.1|
|PC-BF2-2|192.168.22.12|192.168.22.1|
|PC-BF2-3|192.168.22.13|192.168.22.1|
|PC-BF2-4|192.168.22.14|192.168.22.1|
|PC-BF2-5|192.168.22.15|192.168.22.1|

![ScrShot 01](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m4/task4.2/shots/01.png "ScrShot 01")  

Checked the networks by ping. Opened desktop properties, a command prompt, on 4 PCs for example:  
in office A, floor 1: PC-AF1-5 (IP 192.168.11.15), and floor 2: PC-AF2-5 (IP 192.168.12.15);  
in office B, floor 1: PC-BF1-5 (IP 192.168.21.15), and floor 2: PC-BF2-5 (IP 192.168.22.15).  

And provided pings crosswise, between floors and buildings. It works, packets routed well:  

PC-AF1-5 (IP 192.168.11.15)  
```
C:\>ping 192.168.12.15

Pinging 192.168.12.15 with 32 bytes of data:
Reply from 192.168.12.15: bytes=32 time=1ms TTL=127
Reply from 192.168.12.15: bytes=32 time<1ms TTL=127
Reply from 192.168.12.15: bytes=32 time<1ms TTL=127
...
C:\>ping 192.168.22.15

Pinging 192.168.22.15 with 32 bytes of data:
Reply from 192.168.22.15: bytes=32 time<1ms TTL=126
Reply from 192.168.22.15: bytes=32 time<1ms TTL=126
Reply from 192.168.22.15: bytes=32 time=1ms TTL=126
...
```
PC-AF2-5 (IP 192.168.12.15)  
```
C:\>ping 192.168.11.15

Pinging 192.168.11.15 with 32 bytes of data:
Reply from 192.168.11.15: bytes=32 time=1ms TTL=127
Reply from 192.168.11.15: bytes=32 time=1ms TTL=127
Reply from 192.168.11.15: bytes=32 time<1ms TTL=127
...
C:\>ping 192.168.21.15

Pinging 192.168.21.15 with 32 bytes of data:
Reply from 192.168.21.15: bytes=32 time=2ms TTL=126
Reply from 192.168.21.15: bytes=32 time=3ms TTL=126
Reply from 192.168.21.15: bytes=32 time=3ms TTL=126
...
```
PC-BF1-5 (IP 192.168.21.15)  
```
C:\>ping 192.168.22.15

Pinging 192.168.22.15 with 32 bytes of data:
Reply from 192.168.22.15: bytes=32 time=1ms TTL=127
Reply from 192.168.22.15: bytes=32 time<1ms TTL=127
Reply from 192.168.22.15: bytes=32 time<1ms TTL=127
...
C:\>ping 192.168.12.15

Pinging 192.168.12.15 with 32 bytes of data:
Reply from 192.168.12.15: bytes=32 time=14ms TTL=126
Reply from 192.168.12.15: bytes=32 time=2ms TTL=126
Reply from 192.168.12.15: bytes=32 time<1ms TTL=126
...
```
PC-BF2-5 (IP 192.168.22.15)  
```
C:\>ping 192.168.21.15

Pinging 192.168.21.15 with 32 bytes of data:
Reply from 192.168.21.15: bytes=32 time=4ms TTL=127
Reply from 192.168.21.15: bytes=32 time<1ms TTL=127
Reply from 192.168.21.15: bytes=32 time<1ms TTL=127
...
C:\>ping 192.168.11.15

Pinging 192.168.11.15 with 32 bytes of data:
Reply from 192.168.11.15: bytes=32 time=1ms TTL=126
Reply from 192.168.11.15: bytes=32 time=1ms TTL=126
Reply from 192.168.11.15: bytes=32 time<1ms TTL=126
...
```
![ScrShot 02](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m4/task4.2/shots/02.png "ScrShot 02")  

**2.** Created a model of enterprise network. There is 1 building with 4 floors. On the each floors the are 2 workgroups with 3 and five computers respectively. Saved project as `max-4-2-2.pkt`  



**3.** Created a model of enterprise network. There are 5 buildings with 1 floor. Each of buildings has 1 workgroup with 6 computers. The network is based on the 1-port router. Saved project as `max-4-2-3.pkt`  

![ScrShot 03](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m4/task4.2/shots/03.png "ScrShot 03")  

_Thanks for your time!_  


