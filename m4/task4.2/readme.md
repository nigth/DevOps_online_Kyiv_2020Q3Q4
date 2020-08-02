## Task 4.2
### Module 4. Networking Fundamental
___

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
___

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

Assigned IP addresses for PCs (mask 255.255.255.0) and planned VLANs:  

| Host | IP | Gateway | VLAN | Switch | Port |Router sub int.|
|:----:|:--:|:-------:|:----:|:------:|:----:|:----------------:|
|A1-PC1|192.168.1.11|192.168.1.1|VLAN11|Switch-A|FastEthernet1/1|fastEthernet6/0.11|
|A1-PC2|192.168.1.12|192.168.1.1|VLAN11|Switch-A|FastEthernet2/1|fastEthernet6/0.11|
|A1-PC3|192.168.1.13|192.168.1.1|VLAN11|Switch-A|FastEthernet3/1|fastEthernet6/0.11|
| | | |
|A2-PC1|192.168.2.11|192.168.2.1|VLAN12|Switch-A|FastEthernet4/1|fastEthernet6/0.12|
|A2-PC2|192.168.2.12|192.168.2.1|VLAN12|Switch-A|FastEthernet5/1|fastEthernet6/0.12|
|A2-PC3|192.168.2.13|192.168.2.1|VLAN12|Switch-A|FastEthernet6/1|fastEthernet6/0.12|
|A2-PC4|192.168.2.14|192.168.2.1|VLAN12|Switch-A|FastEthernet7/1|fastEthernet6/0.12|
|A2-PC5|192.168.2.15|192.168.2.1|VLAN12|Switch-A|FastEthernet8/1|fastEthernet6/0.12|
| | | |
|B1-PC1|192.168.3.11|192.168.3.1|VLAN13|Switch-B|FastEthernet1/1|fastEthernet7/0.13|
|B1-PC2|192.168.3.12|192.168.3.1|VLAN13|Switch-B|FastEthernet2/1|fastEthernet7/0.13|
|B1-PC3|192.168.3.13|192.168.3.1|VLAN13|Switch-B|FastEthernet3/1|fastEthernet7/0.13|
| | | |
|B2-PC1|192.168.4.11|192.168.4.1|VLAN14|Switch-B|FastEthernet4/1|fastEthernet7/0.14|
|B2-PC2|192.168.4.12|192.168.4.1|VLAN14|Switch-B|FastEthernet5/1|fastEthernet7/0.14|
|B2-PC3|192.168.4.13|192.168.4.1|VLAN14|Switch-B|FastEthernet6/1|fastEthernet7/0.14|
|B2-PC4|192.168.4.14|192.168.4.1|VLAN14|Switch-B|FastEthernet7/1|fastEthernet7/0.14|
|B2-PC5|192.168.4.15|192.168.4.1|VLAN14|Switch-B|FastEthernet8/1|fastEthernet7/0.14|
| | | |
|C1-PC1|192.168.5.11|192.168.5.1|VLAN15|Switch-C|FastEthernet1/1|fastEthernet8/0.15|
|C1-PC2|192.168.5.12|192.168.5.1|VLAN15|Switch-C|FastEthernet2/1|fastEthernet8/0.15|
|C1-PC3|192.168.5.13|192.168.5.1|VLAN15|Switch-C|FastEthernet3/1|fastEthernet8/0.15|
| | | |
|C2-PC1|192.168.6.11|192.168.6.1|VLAN16|Switch-C|FastEthernet4/1|fastEthernet8/0.16|
|C2-PC2|192.168.6.12|192.168.6.1|VLAN16|Switch-C|FastEthernet5/1|fastEthernet8/0.16|
|C2-PC3|192.168.6.13|192.168.6.1|VLAN16|Switch-C|FastEthernet6/1|fastEthernet8/0.16|
|C2-PC4|192.168.6.14|192.168.6.1|VLAN16|Switch-C|FastEthernet7/1|fastEthernet8/0.16|
|C2-PC5|192.168.6.15|192.168.6.1|VLAN16|Switch-C|FastEthernet8/1|fastEthernet8/0.16|
| | | |
|D1-PC1|192.168.7.11|192.168.7.1|VLAN17|Switch-D|FastEthernet1/1|fastEthernet9/0.17|
|D1-PC2|192.168.7.12|192.168.7.1|VLAN17|Switch-D|FastEthernet2/1|fastEthernet9/0.17|
|D1-PC3|192.168.7.13|192.168.7.1|VLAN17|Switch-D|FastEthernet3/1|fastEthernet9/0.17|
| | | |
|D2-PC1|192.168.8.11|192.168.8.1|VLAN18|Switch-D|FastEthernet4/1|fastEthernet9/0.18|
|D2-PC2|192.168.8.12|192.168.8.1|VLAN18|Switch-D|FastEthernet5/1|fastEthernet9/0.18|
|D2-PC3|192.168.8.13|192.168.8.1|VLAN18|Switch-D|FastEthernet6/1|fastEthernet9/0.18|
|D2-PC4|192.168.8.14|192.168.8.1|VLAN18|Switch-D|FastEthernet7/1|fastEthernet9/0.18|
|D2-PC5|192.168.8.15|192.168.8.1|VLAN18|Switch-D|FastEthernet8/1|fastEthernet9/0.18|

![ScrShot 03](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m4/task4.2/shots/03.png "ScrShot 03")  

Configured routing on Router-1:  
http://routeworld.ru/set-i-internet/web_practice/page,3,166-staticheskaya-marshrutizaciya-na-cisco.html  
For the 1st floor A:  
```
Router1>enable
Router1#conf t
Router1(config)#interface fastEthernet6/0.11
Router1(config-subif)#encapsulation dot1Q 11
Router1(config-subif)#ip address 192.168.1.1 255.255.255.0
Router1(config-subif)#exit

Router1(config)#interface fastEthernet 6/0.12
Router1(config-subif)#encapsulation dot1Q 12
Router1(config-subif)#ip address 192.168.2.1 255.255.255.0
Router1(config-subif)#exit

Router1(config)#exit
Router1#write
Building configuration...
[OK]
Router1#copy running-config startup-config
Destination filename [startup-config]? 
Building configuration...
[OK]
```
For the 2nd floor B:  
```
Router1>enable
Router1#conf t
Router1(config)#interface fastEthernet7/0.13
Router1(config-subif)#encapsulation dot1Q 13
Router1(config-subif)#ip address 192.168.3.1 255.255.255.0
Router1(config-subif)#exit

Router1(config)#interface fastEthernet 7/0.14
Router1(config-subif)#encapsulation dot1Q 14
Router1(config-subif)#ip address 192.168.4.1 255.255.255.0
Router1(config-subif)#exit

Router1(config)#exit
Router1#write
Building configuration...
[OK]
Router1#copy running-config startup-config
Destination filename [startup-config]? 
Building configuration...
```
For the 3rd floor C:  
```
Router1(config)#interface fastEthernet8/0.15
Router1(config-subif)#encapsulation dot1Q 15
Router1(config-subif)#ip address 192.168.5.1 255.255.255.0

Router1(config)#interface fastEthernet 8/0.16
Router1(config-subif)#encapsulation dot1Q 16
Router1(config-subif)#ip address 192.168.6.1 255.255.255.0

Router1#write
Router1#copy running-config startup-config
```
For the 4th floor D:  
```
Router1(config)#interface fastEthernet9/0.17
Router1(config-subif)#encapsulation dot1Q 17
Router1(config-subif)#ip address 192.168.7.1 255.255.255.0

Router1(config)#interface fastEthernet 9/0.18
Router1(config-subif)#encapsulation dot1Q 18
Router1(config-subif)#ip address 192.168.8.1 255.255.255.0

Router1#write
Router1#copy running-config startup-config
```
Configured VLANs on switches:  
http://routeworld.ru/set-i-internet/web_practice/page,4,166-staticheskaya-marshrutizaciya-na-cisco.html  
Switch-A:  
```
SwitchA(config)#vlan 11
VLAN 11 added:
    Name: VLAN0011
SwitchA(vlan)#vlan 12
VLAN 12 added:
    Name: VLAN0012
SwitchA(vlan)#exit

SwitchA(config)#interface FastEthernet1/1
SwitchA(config-if)#switchport access vlan 11
SwitchA(vlan)#exit
SwitchA(config)#interface FastEthernet2/1
SwitchA(config-if)#switchport access vlan 11
SwitchA(vlan)#exit
SwitchA(config)#interface FastEthernet3/1
SwitchA(config-if)#switchport access vlan 11
SwitchA(vlan)#exit

SwitchA(config)#interface FastEthernet4/1
SwitchA(config-if)#switchport access vlan 12
SwitchA(config-if)#exit
SwitchA(config)#interface FastEthernet5/1
SwitchA(config-if)#switchport access vlan 12
SwitchA(config-if)#exit
SwitchA(config)#interface FastEthernet6/1
SwitchA(config-if)#switchport access vlan 12
SwitchA(config-if)#exit
SwitchAconfig)#interface FastEthernet7/1
SwitchA(config-if)#switchport access vlan 12
SwitchA(config-if)#exit
SwitchA(config)#interface FastEthernet8/1
SwitchA(config-if)#switchport access vlan 12
SwitchA(config-if)#exit

SwitchA(config)#interface vlan 11
SwitchA(config-if)#ip address 192.168.1.1 255.255.255.0
SwitchA(config-if)#exit
SwitchA(config)#interface vlan 12
SwitchA(config-if)#ip address 192.168.2.1 255.255.255.0
SwitchA(config-if)#exit

SwitchA(config)#interface fastEthernet0/1
SwitchA(config-if)#switchport mode trunk
SwitchA(config-if)#switchport trunk allowed vlan 11-12
SwitchA(config-if)#exit

SwitchA(config)#exit
SwitchA#write
Building configuration...
[OK]
SwitchA#copy running-config startup-config
Destination filename [startup-config]? 
Building configuration...
[OK]
```
Checked how network works on Floor A between groups A1 and A2 - Ok!  
![ScrShot 04](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m4/task4.2/shots/04.png "ScrShot 04")  

Switch-B:  
```
SwitchB>enable
SwitchB#conf t
SwitchB(config)#vlan 13
SwitchB(config-vlan)#exit
SwitchB(config)#vlan 14
SwitchB(config-vlan)#exit

SwitchB(config)#interface FastEthernet1/1
SwitchB(config-if)#switchport access vlan 13
SwitchB(config-if)#exit
SwitchB(config)#interface FastEthernet2/1
SwitchB(config-if)#switchport access vlan 13
SwitchB(config-if)#exit
SwitchB(config)#interface FastEthernet3/1
SwitchB(config-if)#switchport access vlan 13
SwitchB(config-if)#exit

SwitchB(config)#interface FastEthernet4/1
SwitchB(config-if)#switchport access vlan 14
SwitchB(config-if)#exit
SwitchB(config)#interface FastEthernet5/1
SwitchB(config-if)#switchport access vlan 14
SwitchB(config-if)#exit
SwitchB(config)#interface FastEthernet6/1
SwitchB(config-if)#switchport access vlan 14
SwitchB(config-if)#exit
SwitchBconfig)#interface FastEthernet7/1
SwitchB(config-if)#switchport access vlan 14
SwitchB(config-if)#exit
SwitchB(config)#interface FastEthernet8/1
SwitchB(config-if)#switchport access vlan 14
SwitchB(config-if)#exit

SwitchB(config)#interface vlan 13
SwitchB(config-if)#ip address 192.168.3.1 255.255.255.0
SwitchB(config-if)#exit
SwitchB(config)#interface vlan 14
SwitchB(config-if)#ip address 192.168.4.1 255.255.255.0
SwitchB(config-if)#exit

SwitchB(config)#interface fastEthernet0/1
SwitchB(config-if)#switchport mode trunk
SwitchB(config-if)#switchport trunk allowed vlan 13-14
SwitchB(config-if)#exit

SwitchB(config)#exit
SwitchB#write
Building configuration...
[OK]
SwitchB#copy running-config startup-config
Destination filename [startup-config]? 
Building configuration...
[OK]
```
Checked how network works on Floor B between groups B1 and B2 - Ok!  
![ScrShot 05](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m4/task4.2/shots/05.png "ScrShot 05")  

Created simple PDU for two pairs of PCs: A1-PC1 -> B2-PC2; B2-PC5 -> A1-PC3.  
Checked how network works between Floor A and Floor B. All modeling were successful!  
![ScrShot 06](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m4/task4.2/shots/06.png "ScrShot 06")  

Switch-C:  
```
SwitchC(config)#vlan 15
SwitchC(config-vlan)#interface vlan 15
SwitchC(config-if)#ip address 192.168.5.1 255.255.255.0
SwitchC(config)#vlan 16
SwitchC(config-vlan)#interface vlan 16
SwitchC(config-if)#ip address 192.168.6.1 255.255.255.0

SwitchC(config)#interface FastEthernet1/1
SwitchC(config-if)#switchport access vlan 15
SwitchC(config-if)#interface FastEthernet2/1
SwitchC(config-if)#switchport access vlan 15
SwitchC(config-if)#interface FastEthernet3/1
SwitchC(config-if)#switchport access vlan 15

SwitchC(config-if)#interface FastEthernet4/1
SwitchC(config-if)#switchport access vlan 16
SwitchC(config-if)#interface FastEthernet5/1
SwitchC(config-if)#switchport access vlan 16
SwitchC(config-if)#interface FastEthernet6/1
SwitchC(config-if)#switchport access vlan 16
SwitchC(config-if)#interface FastEthernet7/1
SwitchC(config-if)#switchport access vlan 16
SwitchC(config-if)#interface FastEthernet8/1
SwitchC(config-if)#switchport access vlan 16

SwitchC(config)#interface fastEthernet0/1
SwitchC(config-if)#switchport mode trunk
SwitchC(config-if)#switchport trunk allowed vlan 15-16

SwitchC#write
SwitchC#copy running-config startup-config
```
Checked how network works on Floor C between groups C1 and C2 - Ok!  
![ScrShot 07](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m4/task4.2/shots/07.png "ScrShot 07")  

Switch-D:  
```
SwitchD(config)#vlan 17
SwitchD(config-vlan)#interface vlan 17
SwitchD(config-if)#ip address 192.168.7.1 255.255.255.0
SwitchD(config)#vlan 18
SwitchD(config-vlan)#interface vlan 18
SwitchD(config-if)#ip address 192.168.8.1 255.255.255.0

SwitchD(config)#interface FastEthernet1/1
SwitchD(config-if)#switchport access vlan 17
SwitchD(config-if)#interface FastEthernet2/1
SwitchD(config-if)#switchport access vlan 17
SwitchD(config-if)#interface FastEthernet3/1
SwitchD(config-if)#switchport access vlan 17

SwitchD(config-if)#interface FastEthernet4/1
SwitchD(config-if)#switchport access vlan 18
SwitchD(config-if)#interface FastEthernet5/1
SwitchD(config-if)#switchport access vlan 18
SwitchD(config-if)#interface FastEthernet6/1
SwitchD(config-if)#switchport access vlan 18
SwitchD(config-if)#interface FastEthernet7/1
SwitchD(config-if)#switchport access vlan 18
SwitchD(config-if)#interface FastEthernet8/1
SwitchD(config-if)#switchport access vlan 18

SwitchD(config)#interface fastEthernet0/1
SwitchD(config-if)#switchport mode trunk
SwitchD(config-if)#switchport trunk allowed vlan 17-18

SwitchD#write
SwitchD#copy running-config startup-config
```
Checked how network works on Floor D between groups D1 and D2 - good!  
![ScrShot 08](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m4/task4.2/shots/08.png "ScrShot 08")  

Created simple PDU for two pairs of PCs: C1-PC1 -> D2-PC2; D1-PC3 -> C2-PC5.  
Checked how network works between Floor C and Floor D. All packets were successfull.  
![ScrShot 09](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m4/task4.2/shots/09.png "ScrShot 09")  

So I analyzed how all networks are working. Checked connection randomly crosswide everywhere Ok.  
___

**3.** Created a model of enterprise network. There are 5 buildings with 1 floor. Each of buildings has  
1 workgroup with 6 computers. The network is based on the 1-port router. Saved project as `max-4-2-3.pkt`  

House 1: 192.168.11.0/24 _(Switch-1)_  
House 2: 192.168.12.0/24 _(Switch-2)_  
House 3: 192.168.13.0/24 _(Switch-3)_  
House 4: 192.168.14.0/24 _(Switch-4)_  
House 3: 192.168.15.0/24 _(Switch-5)_  
Took fiber channels between switches of houses in trunk mode.  
Used additional central transport switch _(Switch-6)_ and a router _(Router-7)_.  

Assigned IP addresses for PCs (mask 255.255.255.0) and planned VLANs:  

|PCname|       IP    |   Gateway  | VLAN | Switch |Port on switch |Router sub interf.|
|:----:|:-----------:|:----------:|:----:|:------:|:-------------:|:----------------:|
|H1-PC1|192.168.11.11|192.168.11.1|VLAN11|Switch-1|FastEthernet1/1|FastEthernet0/0.11|
|H1-PC2|192.168.11.12|192.168.11.1|VLAN11|Switch-1|FastEthernet2/1|FastEthernet0/0.11|
|H1-PC3|192.168.11.13|192.168.11.1|VLAN11|Switch-1|FastEthernet3/1|FastEthernet0/0.11|
|H1-PC4|192.168.11.14|192.168.11.1|VLAN11|Switch-1|FastEthernet4/1|FastEthernet0/0.11|
|H1-PC5|192.168.11.15|192.168.11.1|VLAN11|Switch-1|FastEthernet5/1|FastEthernet0/0.11|
|H1-PC6|192.168.11.16|192.168.11.1|VLAN11|Switch-1|FastEthernet6/1|FastEthernet0/0.11|
| | | |
|H2-PC1|192.168.12.11|192.168.12.1|VLAN12|Switch-2|FastEthernet1/1|FastEthernet0/0.12|
|H2-PC2|192.168.12.12|192.168.12.1|VLAN12|Switch-2|FastEthernet2/1|FastEthernet0/0.12|
|H2-PC3|192.168.12.13|192.168.12.1|VLAN12|Switch-2|FastEthernet3/1|FastEthernet0/0.12|
|H2-PC4|192.168.12.14|192.168.12.1|VLAN12|Switch-2|FastEthernet4/1|FastEthernet0/0.12|
|H2-PC5|192.168.12.15|192.168.12.1|VLAN12|Switch-2|FastEthernet5/1|FastEthernet0/0.12|
|H2-PC6|192.168.12.16|192.168.12.1|VLAN12|Switch-2|FastEthernet6/1|FastEthernet0/0.12|
| | | |
|H3-PC1|192.168.13.11|192.168.13.1|VLAN13|Switch-3|FastEthernet1/1|FastEthernet0/0.13|
|H3-PC2|192.168.13.12|192.168.13.1|VLAN13|Switch-3|FastEthernet2/1|FastEthernet0/0.13|
|H3-PC3|192.168.13.13|192.168.13.1|VLAN13|Switch-3|FastEthernet3/1|FastEthernet0/0.13|
|H3-PC4|192.168.13.14|192.168.13.1|VLAN13|Switch-3|FastEthernet4/1|FastEthernet0/0.13|
|H3-PC5|192.168.13.15|192.168.13.1|VLAN13|Switch-3|FastEthernet5/1|FastEthernet0/0.13|
|H3-PC6|192.168.13.16|192.168.13.1|VLAN13|Switch-3|FastEthernet6/1|FastEthernet0/0.13|
| | | |
|H4-PC1|192.168.14.11|192.168.14.1|VLAN14|Switch-4|FastEthernet1/1|FastEthernet0/0.14|
|H4-PC2|192.168.14.12|192.168.14.1|VLAN14|Switch-4|FastEthernet2/1|FastEthernet0/0.14|
|H4-PC3|192.168.14.13|192.168.14.1|VLAN14|Switch-4|FastEthernet3/1|FastEthernet0/0.14|
|H4-PC4|192.168.14.14|192.168.14.1|VLAN14|Switch-4|FastEthernet4/1|FastEthernet0/0.14|
|H4-PC5|192.168.14.15|192.168.14.1|VLAN14|Switch-4|FastEthernet5/1|FastEthernet0/0.14|
|H4-PC6|192.168.14.16|192.168.14.1|VLAN14|Switch-4|FastEthernet6/1|FastEthernet0/0.14|
| | | |
|H5-PC1|192.168.15.11|192.168.15.1|VLAN15|Switch-5|FastEthernet1/1|FastEthernet0/0.15|
|H5-PC2|192.168.15.12|192.168.15.1|VLAN15|Switch-5|FastEthernet2/1|FastEthernet0/0.15|
|H5-PC3|192.168.15.13|192.168.15.1|VLAN15|Switch-5|FastEthernet3/1|FastEthernet0/0.15|
|H5-PC4|192.168.15.14|192.168.15.1|VLAN15|Switch-5|FastEthernet4/1|FastEthernet0/0.15|
|H5-PC5|192.168.15.15|192.168.15.1|VLAN15|Switch-5|FastEthernet5/1|FastEthernet0/0.15|
|H5-PC6|192.168.15.16|192.168.15.1|VLAN15|Switch-5|FastEthernet6/1|FastEthernet0/0.15|

![ScrShot 10](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m4/task4.2/shots/10.png "ScrShot 10")  

Conigured switches in the houses.  
House 1, **Switch-1**:  
```
vlan 11
interface vlan 11
ip address 192.168.11.1 255.255.255.0

interface FastEthernet1/1
switchport access vlan 11
interface FastEthernet2/1
switchport access vlan 11
interface FastEthernet3/1
switchport access vlan 11
interface FastEthernet4/1
switchport access vlan 11
interface FastEthernet5/1
switchport access vlan 11
interface FastEthernet6/1
switchport access vlan 11

interface fastEthernet0/1
switchport mode trunk
switchport trunk allowed vlan 11
```
House 2, **Switch-2**:  
```
vlan 12
interface vlan 12
ip address 192.168.12.1 255.255.255.0

interface FastEthernet1/1
switchport access vlan 12
interface FastEthernet2/1
switchport access vlan 12
interface FastEthernet3/1
switchport access vlan 12
interface FastEthernet4/1
switchport access vlan 12
interface FastEthernet5/1
switchport access vlan 12
interface FastEthernet6/1
switchport access vlan 12

interface fastEthernet0/1
switchport mode trunk
switchport trunk allowed vlan 12
```
House 3, **Switch-3**:  
```
vlan 13
interface vlan 13
ip address 192.168.13.1 255.255.255.0

interface FastEthernet1/1
switchport access vlan 13
interface FastEthernet2/1
switchport access vlan 13
interface FastEthernet3/1
switchport access vlan 13
interface FastEthernet4/1
switchport access vlan 13
interface FastEthernet5/1
switchport access vlan 13
interface FastEthernet6/1
switchport access vlan 13

interface fastEthernet0/1
switchport mode trunk
switchport trunk allowed vlan 13
```
House 4, **Switch-4**:  
```
vlan 14
interface vlan 14
ip address 192.168.14.1 255.255.255.0

interface FastEthernet1/1
switchport access vlan 14
interface FastEthernet2/1
switchport access vlan 14
interface FastEthernet3/1
switchport access vlan 14
interface FastEthernet4/1
switchport access vlan 14
interface FastEthernet5/1
switchport access vlan 14
interface FastEthernet6/1
switchport access vlan 14

interface fastEthernet0/1
switchport mode trunk
switchport trunk allowed vlan 14
```
House 5, **Switch-5**:  
```
vlan 15
interface vlan 15
ip address 192.168.15.1 255.255.255.0

interface FastEthernet1/1
switchport access vlan 15
interface FastEthernet2/1
switchport access vlan 15
interface FastEthernet3/1
switchport access vlan 15
interface FastEthernet4/1
switchport access vlan 15
interface FastEthernet5/1
switchport access vlan 15
interface FastEthernet6/1
switchport access vlan 15

interface fastEthernet0/1
switchport mode trunk
switchport trunk allowed vlan 15
```
Conigured additional central transport switch, **Switch-6**:  
```
vlan 11
interface vlan 11
ip address 192.168.11.1 255.255.255.0
vlan 12
interface vlan 12
ip address 192.168.12.1 255.255.255.0
vlan 13
interface vlan 13
ip address 192.168.13.1 255.255.255.0
vlan 14
interface vlan 14
ip address 192.168.14.1 255.255.255.0
vlan 15
interface vlan 15
ip address 192.168.15.1 255.255.255.0

interface FastEthernet1/1
switchport mode trunk
switchport  trunk allowed vlan 11
interface FastEthernet2/1
switchport mode trunk
switchport  trunk allowed vlan 12
interface FastEthernet3/1
switchport mode trunk
switchport  trunk allowed vlan 13
interface FastEthernet4/1
switchport mode trunk
switchport  trunk allowed vlan 14
interface FastEthernet5/1
switchport mode trunk
switchport  trunk allowed vlan 15

interface fastEthernet0/1
switchport mode trunk
switchport trunk allowed vlan 11-15
```
Configured router **Router-7**:  
```
interface fastEthernet0/0.11
encapsulation dot1Q 11
ip address 192.168.11.1 255.255.255.0

interface fastEthernet0/0.12
encapsulation dot1Q 12
ip address 192.168.12.1 255.255.255.0

interface fastEthernet0/0.13
encapsulation dot1Q 13
ip address 192.168.13.1 255.255.255.0

interface fastEthernet0/0.14
encapsulation dot1Q 14
ip address 192.168.14.1 255.255.255.0

interface fastEthernet0/0.15
encapsulation dot1Q 15
ip address 192.168.15.1 255.255.255.0
```
___

_Thanks for your time!_  





