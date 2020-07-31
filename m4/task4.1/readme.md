## Task 4.1
### Module 4. Networking Fundamentals

**1.** Created project from 4 PC and 1 Hub.  

**2.** Saved project as `max-4-1.pkt`  
![ScrShot 01](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m4/task4.1/shots/01.png "ScrShot 01")  

**3.** Assigned IP addresses for PCs.  

| Host | IP | Mask |
|:----:|:--:|:----:|
|PC0|192.168.0.1|255.255.255.0|
|PC1|192.168.0.2|255.255.255.0|
|PC2|192.168.0.3|255.255.255.0|
|PC3|192.168.0.4|255.255.255.0|

**4.** Checked the network using Simple PDU from PC1 to PC2 - it works.  

**5.** Simulated ICMP from PC1 to PC2, capture and play.  
![ScrShot 02](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m4/task4.1/shots/02.png "ScrShot 02")  

**6.** Watched the ICMP packets in a Simulation Panel.  
![ScrShot 03](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m4/task4.1/shots/03.png "ScrShot 03")  

**7.** Watched info about packets in accordance with OSI model.  
![ScrShot 04](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m4/task4.1/shots/04.png "ScrShot 04")  
**Analyzed situation:** FastEthernet0 receives the frame.  

**8.** Deleted IP addresses from PC0-PC3 and saw, that network doesn't work. Repeated points 5-7:  

**8.5.** Simulated ICMP from PC1 to PC2, capture and play - packets don't go.  
![ScrShot 05](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m4/task4.1/shots/05.png "ScrShot 05")  

**8.6.** Watched the ICMP packets in a Simulation Panel - nothing works.  
![ScrShot 06](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m4/task4.1/shots/06.png "ScrShot 06")  

**8.7.** Watched info about packets in accordance with OSI model, see ICMP message type 8.  
![ScrShot 07](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m4/task4.1/shots/07.png "ScrShot 07")  

**Analyzed differences:**  
- The Ping process starts the next ping request.  
- The Ping process creates an ICMP Echo Request message and sends it to the lower process.  
- The port does not have an IP address.  
- The device drops the packet.  

**9.** Created proect from PC0-PC5, Server. Both of hubs are connected by crossover.  
![ScrShot 08](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m4/task4.1/shots/08.png "ScrShot 08")  

**10.** Assigned IP addresses for hosts.   

| Host | IP | Mask |
|:----:|:--:|:----:|
|PC0|192.168.0.1|255.255.255.0|
|PC1|192.168.0.2|255.255.255.0|
|PC2|192.168.0.3|255.255.255.0|
|PC3|192.168.0.4|255.255.255.0|
|**Server**|**192.168.0.5**|255.255.255.0|
|PC4|192.168.0.6|255.255.255.0|
|PC5|192.168.0.7|255.255.255.0|

**11.** Checked the network using Simple PDU from PC1 to PC4 - it works.  
![ScrShot 09](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m4/task4.1/shots/09.png "ScrShot 09")  

**12.** Created project from 4 PCs and a Switch Catalyst 2950-24.  

**13.** Repeated steps 3-7:  

**13.3.** Assigned IP addresses for PCs.  

| Host | IP | Mask |
|:----:|:--:|:----:|
|PC0|192.168.0.1|255.255.255.0|
|PC1|192.168.0.2|255.255.255.0|
|PC2|192.168.0.3|255.255.255.0|
|PC3|192.168.0.4|255.255.255.0|

**13.4.** Checked the network using Simple PDU from PC2 to PC3 - it works.  

**13.5.** Simulated ICMP from PC2 to PC3, capture and play.  

**13.6.** Watched the ICMP packets in a Simulation Panel.  

**13.7.** Watched info about packets in accordance with OSI model.  
![ScrShot 10](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m4/task4.1/shots/10.png "ScrShot 10")  

**Analyzed difference between topology 1 (with a Hub) and topology 3 (with a Switch):**  
- instead of ICMP packets, we can see another protocols working: ARP, STP, DTP.  
- the ICMP packets aren't broadcasting, a switch delivers them only to one destination.  

**14.** Expanded project to 8 PCs and 2 Switches.  

**15.** Added ports on the switches in a Physical tab.  

**16.** Assigned IP addresses for PCs.  

| Host | IP | Mask |
|:----:|:--:|:----:|
|PC0|192.168.0.1|255.255.255.0|
|PC1|192.168.0.2|255.255.255.0|
|PC2|192.168.0.3|255.255.255.0|
|PC3|192.168.0.4|255.255.255.0|
|PC4|192.168.0.5|255.255.255.0|
|PC5|192.168.0.6|255.255.255.0|
|PC6|192.168.0.7|255.255.255.0|
|PC7|192.168.0.8|255.255.255.0|

**17.** Checked network using Simple PDU from PC3 to PC7, it works: **`FastEthernet0 receives the frame.`**  
![ScrShot 11](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m4/task4.1/shots/11.png "ScrShot 11")  

**18.** Splitted the network in two by Router-PT with Fiber.  

**19.** Change assigned IP addresses for РС4 – РС7 to others.  

| Host | IP | Mask |
|:----:|:--:|:----:|
|PC0|192.168.0.1|255.255.255.0|
|PC1|192.168.0.2|255.255.255.0|
|PC2|192.168.0.3|255.255.255.0|
|PC3|192.168.0.4|255.255.255.0|
|PC4|**192.168.1.1**|255.255.255.0|
|PC5|**192.168.1.2**|255.255.255.0|
|PC6|**192.168.1.3**|255.255.255.0|
|PC7|**192.168.1.4**|255.255.255.0|

**20.** Turned on router's ports and assigned them IP addresses.  

| Port | IP | Mask |
|:----:|:--:|:----:|
|FE4/0|192.168.0.10|255.255.255.0|
|FE4/1|192.168.1.10|255.255.255.0|

Save the router configuration in CLI using command `write` or `copy running-config startup-config`.  

**21.** Assigned a gateway for PCs.  

| Host | Gateway IP |
|:----:|:--:|
|PC0 - PC3|192.168.0.10|
|PC4 - PC5|192.168.1.10|

**22.** Checked network using Simple PDU from PC2 to PC6, it works: **`FastEthernet0 receives the frame.`**  
![ScrShot 12](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m4/task4.1/shots/12.png "ScrShot 12")  

**23.** The main difference between Topology 4 and Topology 6 is that with Router we use two different IP ranges in subnets. And a router provide to ICMP packets a correct destination to the host in other subnet. It opened for us a lot of possibilities for Network segmentation, for more security, and for best performance (instead of using the one big network), etc.  
 
_Thanks for your time!_  
 

