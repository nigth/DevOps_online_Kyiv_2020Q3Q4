## Task 2.2
### Part 1. Work with VirtualBox
:black_square_button: **1. First run VirtualBox and Virtual Machine (VM):**  
:white_check_mark: 1.0. Get acquainted with the structure of the user manual VirtualBox  
:white_check_mark: 1.1. Download the latest stable version: https://www.virtualbox.org/wiki/Linux_Downloads  
```
echo deb [arch=amd64] https://download.virtualbox.org/virtualbox/debian bionic contrib >> /etc/apt/sources.list
wget -q https://www.virtualbox.org/download/oracle_vbox_2016.asc -O- | sudo apt-key add -
wget -q https://www.virtualbox.org/download/oracle_vbox.asc -O- | sudo apt-key add -
sudo apt-get update && sudo apt install virtualbox-6.1
```
also added `Oracle_VM_VirtualBox_Extension_Pack-6.1.12.vbox-extpack`  
:white_check_mark: 1.2. Download the latest stable version of Ubuntu 20.04 LTS Desktop:  
`ubuntu-20.04-desktop-amd64.iso` from https://ubuntu.com/download/desktop  
:white_check_mark: 1.3. Create VM1 and install Ubuntu. Set machine name as **`hp4330yatsyuta`**.  
Name *`hp4330_yatsyuta`* impossible: underline "_" restricted *(only letters, digits and dot "." allowed)*  
:white_check_mark: 1.4. Get acquainted with the possibilities of VM1 control -  
 start, stop, reboot, save state, use Host key and keyboard shortcuts, mouse capture, etc.  
:white_check_mark: 1.5. Clone an existing VM1 by creating a VM2.  
![Screenshot 1](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m2/task2.2/screenshots/scr1vbox.png "Screenshot 1")  
:white_check_mark: 1.6. Create a group of two VM: VM1, VM2 and learn the functions related to groups.  
:white_check_mark: 1.7. For VM1, changing its state, take several different snapshots, forming a branched
tree of snapshots.  
![Screenshot 2](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m2/task2.2/screenshots/scr2vbox.png "Screenshot 2")  
:white_check_mark: 1.8. Export VM1. Save the `vm1.ova` file to disk. Import VM from `vm1.ova` file.  
:black_square_button: **2. Configuration of virtual machines:**  
:white_check_mark: 2.1. Explore VM configuration options (general settings, system settings, display,
storage, audio, network, etc.).  
:white_check_mark: 2.2. Configure the USB to connect the USB ports of the host machine to the VM
[1, ch.3.11].  
:white_check_mark: 2.3. Configure a shared folder to exchange data between the virtual machine and
the host [1, ch.4.3].  
![Screenshot 3](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m2/task2.2/screenshots/scr3vbox.png "Screenshot 3")  
:white_check_mark: 2.4. Configure different network modes for VM1, VM2.  
Check the connection between VM1, VM2, Host, Internet for different network modes.  
Use the `ping` command to do this. Make a table of possible connections.  

| Adapter | VM -> Host | Host -> VM | VM1 <-> VM2 | VM -> Net/Lan | Net/Lan -> VM |
|:-------:|:----------:|:----------:|:-----------:|:-------------:|:-------------:|
|Host only| YES | YES| YES | no | no |
|Internal | no  | no | YES | no | no | 
|Bridge   | YES | YES | YES | YES | YES | 
|NAT      | YES | p/f | no | YES | p/f |
|NAT service| YES | p/f | YES | YES | p/f |
*p/f - Port Forwarding

:black_square_button: **3. Work with CLI through VBoxManage:**  
:white_check_mark: 3.1. Open the BASH terminal.  
:white_check_mark: 3.2. Examine the purpose and execute the basic commands of  
VBoxManage list, showvminfo, createvm, startvm, modifyvm, clonevm, snapshot, controlvm.  
```
$ vboxmanage list vms
"VM1" {0765ea84-2504-46a5-ba6c-cb4dfa944aa3}
"VM2" {f917e9b1-1f49-44a2-9766-9e28226171c1}

$ vboxmanage list groups
"/Новая группа"

$ vboxmanage showvminfo VM1
Name:                        VM1
Groups:                      /Новая группа
Guest OS:                    Ubuntu (64-bit)
UUID:                        0765ea84-2504-46a5-ba6c-cb4dfa944aa3
Config file:                 /home/maxim/virtuals/Новая группа/VM1/VM1.vbox
Snapshot folder:             /home/maxim/virtuals/Новая группа/VM1/Snapshots
Log folder:                  /home/maxim/virtuals/Новая группа/VM1/Logs
Hardware UUID:               0765ea84-2504-46a5-ba6c-cb4dfa944aa3
...

```
### Part 2. Work with Vagrant
:white_check_mark: 1. Download and install the required version of Vagrant `vagrant_2.2.9_x86_64.deb`:  
https://www.vagrantup.com/downloads  
https://learn.hashicorp.com/vagrant/getting-started/install  
Check the path to Vagrant bin in the Path variable:
```
$ whereis vagrant
vagrant: /usr/bin/vagrant /opt/vagrant/bin/vagrant
```
:white_check_mark: 2. Run BASH terminal. In the home folder `maxim` create a folder `vagrant_test`:
```
mkdir ~/vagrant_test && cd ~/vagrant_test
```
:white_check_mark: 3. Initialize the environment init hashicorp/precise64 with the default Vagrant  
```
vagrant init hashicorp/precise64
```
:white_check_mark: 4. Run vagrant up and watch for messages during VM boot and startup.  
```
vagrant up
```
![Screenshot 4](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m2/task2.2/screenshots/scr4vagrant.png "Screenshot 4")  
:white_check_mark: 5. Connect to the VM  using SSH, IP address and port listed above (127.0.0.1:2222).  
By default, login - `vagrant` and password are also `vagrant` (or use `default` VM name):  
```
ssh vagrant@127.0.0.1:2222
vagrant ssh default
```
:white_check_mark: 6. Record the date and time by executing the date command  
```
$ date
Wed Jul 15 15:38:56 UTC 2020
```
:white_check_mark: 7. Stop and delete the created VM.  
```
vagrant halt
vagrant destroy
```
![Screenshot 5](https://github.com/nigth/DevOps_online_Kyiv_2020Q3Q4/blob/master/m2/task2.2/screenshots/scr5vagrant.png "Screenshot 5")  
:white_check_mark: 8. Create your own Vagrant box  
:negative_squared_cross_mark: 9. *(optional)* Create a test environment from a few servers.  
Servers' parameters are chosen independently by the student.  

  

