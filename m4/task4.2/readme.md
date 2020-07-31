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

PC-AF1-5 (IP 192.168.11.15):  
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
PC-AF2-5 (IP 192.168.12.15):  
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
PC-BF1-5 (IP 192.168.21.15):  
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
PC-BF2-5 (IP 192.168.22.15):  
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

**2.** Created a model of enterprise network. There is 1 building with 4 floors.  
On each floors the are 2 groups with 3 and 5 computers. Saved project as `max-4-2-2.pkt`  

**Floor A** _(Switch-A)_  
Group A1 (3 PCs): 192.168.1.0/24  
Group A2 (5 PCs): 192.168.2.0/24  
**Floor B** _(Switch-B)_  
Group B1 (3 PCs): 192.168.3.0/24  
Group B2 (5 PCs): 192.168.4.0/24  
**Floor C** _(Switch-C)_  
Group C1 (3 PCs): 192.168.5.0/24  
Group C2 (5 PCs): 192.168.6.0/24  
**Floor D** _(Switch-D)_  
Group D1 (3 PCs): 192.168.7.0/24  
Group D2 (5 PCs): 192.168.8.0/24  

**RIP** table on a Router-1 consists all our networks:  
192.168.1.0  
192.168.2.0  
192.168.3.0  
192.168.4.0  
192.168.5.0  
192.168.6.0  
192.168.7.0  
192.168.8.0  

Assigned IP addresses for computers (mask is everything 255.255.255.0):

| Host | IP |Gateway|
|:----:|:--:|:-----:|
|F1-G1-P1|192.168.1.11|192.168.1.1|
|F1-G1-P2|192.168.1.12|192.168.1.1|
|F1-G1-P3|192.168.1.13|192.168.1.1|
| | | |
|F1-G2-P1|192.168.2.11|192.168.1.1|
|F1-G2-P2|192.168.2.12|192.168.1.1|
|F1-G2-P3|192.168.2.13|192.168.1.1|
|F1-G2-P4|192.168.2.14|192.168.1.1|
|F1-G2-P5|192.168.2.15|192.168.1.1|
| | | |
| | | |
|F2-G1-P1|192.168.3.11|192.168.2.1|
|F2-G1-P2|192.168.3.12|192.168.2.1|
|F2-G1-P3|192.168.3.13|192.168.2.1|
| | | |
|F2-G2-P1|192.168.4.11|192.168.2.1|
|F2-G2-P2|192.168.4.12|192.168.2.1|
|F2-G2-P3|192.168.4.13|192.168.2.1|
|F2-G2-P4|192.168.4.14|192.168.2.1|
|F2-G2-P5|192.168.4.15|192.168.2.1|
| | | |
| | | |
|F3-G1-P1|192.168.5.11|192.168.3.1|
|F3-G1-P2|192.168.5.12|192.168.3.1|
|F3-G1-P3|192.168.5.13|192.168.3.1|
| | | |
|F3-G2-P1|192.168.6.11|192.168.3.1|
|F3-G2-P2|192.168.6.12|192.168.3.1|
|F3-G2-P3|192.168.6.13|192.168.3.1|
|F3-G2-P4|192.168.6.14|192.168.3.1|
|F3-G2-P5|192.168.6.15|192.168.3.1|
| | | |
| | | |
|F4-G1-P1|192.168.7.11|192.168.4.1|
|F4-G1-P2|192.168.7.12|192.168.4.1|
|F4-G1-P3|192.168.7.13|192.168.4.1|
| | | |
|F4-G2-P1|192.168.8.11|192.168.4.1|
|F4-G2-P2|192.168.8.12|192.168.4.1|
|F4-G2-P3|192.168.8.13|192.168.4.1|
|F4-G2-P4|192.168.8.14|192.168.4.1|
|F4-G2-P5|192.168.8.15|192.168.4.1|

![ScrShot 03](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m4/task4.2/shots/03.png "ScrShot 03")  


![ScrShot 04](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m4/task4.2/shots/04.png "ScrShot 04")  


**3.** Created a model of enterprise network. There are 5 buildings with 1 floor. Each of buildings has 1 workgroup with 6 computers. The network is based on the 1-port router. Saved project as `max-4-2-3.pkt`  

![ScrShot 05](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m4/task4.2/shots/05.png "ScrShot 05")  


![ScrShot 06](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m4/task4.2/shots/06.png "ScrShot 06")  

_Thanks for your time!_  


