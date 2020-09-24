## Task 6a.2.
### Module 6a. Linux Networking
#### Configuring DHCP, DNS servers and dynamic routing using OSPF protocol

:heavy_check_mark: **6a.2.1.** Use already created internal-network for three VMs (VM1-VM3).  
VM1 has NAT and internal, VM2, VM3 – internal only interfaces:  
![ScrShot 01](scr/01.png "ScrShot 01")  

Modeling in the Cisco PacketTracer. For the VM3 I used a clone of VM1 with new mac addresses.  
![ScrShot 02](scr/02.png "ScrShot 02")  

:white_check_mark: **6a.2.2.** Install and configure DHCP server on VM1.  
_(3 ways: using  , DNSMASQ and ISC-DHSPSERVER)_. I prefer to use a DNSMASQ DHCP on `enp0s8` interface.  
```bash
sudo apt-get install dnsmasq
sudo vim /etc/dnsmasq.conf
---
interface=enp0s8
domain=myhome.inc
dhcp-range=192.168.1.20,192.168.1.100,24h
dhcp-option=3,192.168.1.1
dhcp-option=1,255.255.255.0
dhcp-host=08:00:27:be:a8:ab,bunta20,192.168.1.1
---
dnsmasq --test
sudo service dnsmasq restart
sudo service dnsmasq status
```
But I got an error message about 53 TCP port is already in use.  
`sudo netstat -lntp`  
So I changed settings for `systemd-resolve` as described in the article:  
https://andreyex.ru/ubuntu/kak-osvobodit-port-53-ispolzuemyj-systemd-resolved-v-ubuntu/  

![ScrShot 03](scr/03.png "ScrShot 03")  

:white_check_mark: **6a.2.3.** Check VM2 and VM3 for obtaining network addresses from DHCP server.  

![ScrShot 04](scr/04.png "ScrShot 04")  

:white_check_mark: **6a.2.4.** Using existed network for three VMs (from p.1),  
install and configure DNS server on VM1. _(using DNSMASQ, BIND9)._ I prefer to use a DNSMASQ DNS.  

![ScrShot 05](scr/05.png "ScrShot 05")  

:white_check_mark: **6a.2.5.** Check VM2 and VM3 for gaining access to DNS server (naming services).  

![ScrShot 06](scr/06.png "ScrShot 06")  

:negative_squared_cross_mark: **6a.2.6.** _optional, addition task_  
Using the scheme which follows, configure dynamic routing using OSPF protocol.  

:white_check_mark: **6a.2.7.**  Check results.  

![ScrShot 07](scr/07.png "ScrShot 07")  

![ScrShot 08](scr/08.png "ScrShot 08")  

![ScrShot 09](scr/09.png "ScrShot 09")  

![ScrShot 10.](scr/10.png "ScrShot 10")  
___
 
_Thanks for your time!_  
