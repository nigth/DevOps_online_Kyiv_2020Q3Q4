## Task 4.1
### Module 4. Networking Fundamentals
**1.** Created project from 4 PC and 1 Hub.  
**2.** Saved project as `max-4-1.pkt`  
![ScrShot 01](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m4/task4.1/shots/01.png "ScrShot 01")  
**3.** Assigned IP addresses for PCs.  

| Host | IP | MASK |
|:--:|:--:|:----:|
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
**Analyzed situation:**  
- FastEthernet0 receives the frame.
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

| Host | IP | MASK |
|:--:|:--:|:----:|
|PC0|192.168.0.1|255.255.255.0|
|PC1|192.168.0.2|255.255.255.0|
|PC2|192.168.0.3|255.255.255.0|
|PC3|192.168.0.4|255.255.255.0|
|Server|192.168.0.5|255.255.255.0|
|PC4|192.168.0.6|255.255.255.0|
|PC5|192.168.0.7|255.255.255.0|
**11.** Checked the network using Simple PDU from PC1 to PC4 - it works.  
![ScrShot 09](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m4/task4.1/shots/09.png "ScrShot 09")  
**12.**  
**13.**  
**14.**  
**15.**  
**16.**  
**17.**  
**18.**  
**19.**  
**20.**  
**21.**  
**22.**  
**23.**  
 

