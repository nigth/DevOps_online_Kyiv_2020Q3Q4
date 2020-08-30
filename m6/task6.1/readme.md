## Task 6a.1
### Module 6a. Linux Networking
#### IP routing

**6a.1.1.** Create virtual machines connection according to figure 1:  
![ScrShot 01](scr/01.png "ScrShot 01")  
Modeling in the Cisco PacketTracer:  
![ScrShot 02](scr/02.png "ScrShot 02")  

**6a.1.2.** VM2 has one interface (internal), VM1 has 2 interfaces (NAT and internal).  
Configure all network interfaces in order to make VM2 has an access to the Internet (iptables, forward, masquerade).  

```
# UBUNTU
ifconfig -a
sudo ifconfig enp0s8 192.168.1.1 netmask 255.255.255.0
ifconfig -a
```
```
# CENTOS
ifconfig -a
sudo ifconfig enp0s8 192.168.1.2 netmask 255.255.255.0
ifconfig -a
```

**6a.1.3.** Check the route from VM2 to Host.  

![ScrShot 03](scr/03.png "ScrShot 03")  

**6a.1.4.** Check the access to the Internet, (just ping, for example, 8.8.8.8).  

![ScrShot 04](scr/04.png "ScrShot 04")  

**6a.1.5.** Determine, which resource has an IP address 8.8.8.8.  

![ScrShot 05](scr/05.png "ScrShot 05")  

**6a.1.6.** Determine, which IP address belongs to resource epam.com.  

![ScrShot 06](scr/06.png "ScrShot 06")  

**6a.1.7.** Determine the default gateway for your HOST and display routing table.  

![ScrShot 07](scr/07.png "ScrShot 07")  

**6a.1.8.** Trace the route to google.com.  

![ScrShot 08](scr/08.png "ScrShot 08")  

![ScrShot 09](scr/09.png "ScrShot 09")  

![ScrShot 10.](scr/10.png "ScrShot 10")  
___
 
_Thanks for your time!_  
