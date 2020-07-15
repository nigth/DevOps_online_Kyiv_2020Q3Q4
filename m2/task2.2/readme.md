## Task 2.2
### PART 1. WORK WITH VIRTUALBOX
1. First run VirtualBox and Virtual Machine (VM).  
:white_check_mark: 1.1. Get acquainted with the structure of the user manual VirtualBox  
:white_check_mark: 1.2 Download the latest stable version: https://www.virtualbox.org/wiki/Linux_Downloads  
```
echo deb [arch=amd64] https://download.virtualbox.org/virtualbox/debian bionic contrib >> /etc/apt/sources.list
wget -q https://www.virtualbox.org/download/oracle_vbox_2016.asc -O- | sudo apt-key add -
wget -q https://www.virtualbox.org/download/oracle_vbox.asc -O- | sudo apt-key add -
sudo apt-get update
sudo apt-get install virtualbox-6.1
```
also added `Oracle_VM_VirtualBox_Extension_Pack-6.1.12.vbox-extpack`  
:white_check_mark: 1.2 Download the latest stable version of Ubuntu 20.04 LTS Desktop:  
`ubuntu-20.04-desktop-amd64.iso` from https://ubuntu.com/download/desktop  
:white_check_mark: 1.3 Create VM1 and install Ubuntu. Set machine name as *hp4330_yatsyuta*  
:black_square_button: 1.4 Get acquainted with the possibilities of VM1 control - start, stop, reboot, save state,
use Host key and keyboard shortcuts, mouse capture, etc. [1, ch.1.9].  
:black_square_button: 1.5 Clone an existing VM1 by creating a VM2 [1, ch.1.14].  
:black_square_button: 1.6 Create a group of two VM: VM1, VM2 and learn the functions related to groups [1,
п.1.10].  
:black_square_button: 1.7 For VM1, changing its state, take several different snapshots, forming a branched
tree of snapshots [1, ch.1.11].  
:black_square_button: 1.8 Export VM1. Save the *.ova file to disk. Import VM from *.ova file [1, ch.1.15].
2. Configuration of virtual machines.  
:black_square_button: 2.1 Explore VM configuration options (general settings, system settings, display,
storage, audio, network, etc.).  
:black_square_button: 2.2 Configure the USB to connect the USB ports of the host machine to the VM
[1, ch.3.11].  
:black_square_button: 2.3 Configure a shared folder to exchange data between the virtual machine and
the host [1, ch.4.3].  
:black_square_button: 2.4 Configure different network modes for VM1, VM2. Check the connection
between VM1, VM2, Host, Internet for different network modes. You can use the ping
command to do this. Make a table of possible connections.  
3. Work with CLI through VBoxManage.  
:black_square_button: 3.1 Run the cmd.exe command line.  
:black_square_button: 3.2 Examine the purpose and execute the basic commands of VBoxManage list,  
showvminfo, createvm, startvm, modifyvm, clonevm, snapshot, controlvm [1, ch.8].  

