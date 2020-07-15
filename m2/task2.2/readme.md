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
:black_square_button: 1.5. Clone an existing VM1 by creating a VM2.  
:black_square_button: 1.6. Create a group of two VM: VM1, VM2 and learn the functions related to groups [1,
п.1.10].  
:black_square_button: 1.7. For VM1, changing its state, take several different snapshots, forming a branched
tree of snapshots [1, ch.1.11].  
:black_square_button: 1.8. Export VM1. Save the *.ova file to disk. Import VM from *.ova file [1, ch.1.15].
Screenshot 1:  
:black_square_button: **2. Configuration of virtual machines:**  
:black_square_button: 2.1. Explore VM configuration options (general settings, system settings, display,
storage, audio, network, etc.).  
:black_square_button: 2.2. Configure the USB to connect the USB ports of the host machine to the VM
[1, ch.3.11].  
:black_square_button: 2.3. Configure a shared folder to exchange data between the virtual machine and
the host [1, ch.4.3].  
:black_square_button: 2.4. Configure different network modes for VM1, VM2.  
Check the connection between VM1, VM2, Host, Internet for different network modes.  
Use the `ping` command to do this. Make a table of possible connections.  
Screenshot 2:  
:black_square_button: **3. Work with CLI through VBoxManage:**  
:black_square_button: 3.1. Run the cmd.exe command line.  
:black_square_button: 3.2. Examine the purpose and execute the basic commands of VBoxManage list,  
showvminfo, createvm, startvm, modifyvm, clonevm, snapshot, controlvm [1, ch.8].  
Screenshot 3:  
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
:black_square_button: 3. Initialize the environment init hashicorp/precise64 with the default Vagrant  
```
vagrant init hashicorp/precise64
```
:black_square_button: 4. Run vagrant up and watch for messages during VM boot and startup.  
```
vagrant up
```
:black_square_button: 5. Connect to the VM  using SSH, IP address and port listed above (127.0.0.1:2222).  
By default, login - `vagrant` and password are also `vagrant`  
```
ssh vagrant@127.0.0.1:2222
```
:black_square_button: 6. Record the date and time by executing the date command  
```
date
```
:black_square_button: 7. Stop and delete the created VM.  
```
vagrant halt
vagrant destroy
```
:black_square_button: 8. Create your own Vagrant box  
:negative_squared_cross_mark: 9. *(optional)* Create a test environment from a few servers.  
Servers' parameters are chosen independently by the student.  
Screenshot 4:  
