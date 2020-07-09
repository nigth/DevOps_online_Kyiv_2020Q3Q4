There are two types of hypervisors.  
First type hypervisors run on a barebone server and don't needs any operation system.   
It works more quickly and uses for enterprise vitualization.  
Second type hypervisors needs an operation system for work their monitor.  
Through it virtual machines get access to the hardware.   
This kind of systems usually uses on the desktops for personal goals.  

The most popular hypervisors used to infrastructure (first type) are:
- KVM
- ESXi
- Hyper-V

The most popular hypervisors of second type are:
- OpenVZ
- Oracle VirtualBox
- VMware Workstation

Hyper-V and VMware are proprietary products, and KVM is an opensource solution.  
  
Hyper-V is the Microsoft product, so it is based on the MS Server.  
Often it is a Core version without GUI, only with command line interface.  
But it has a very useful remote admin console.  

ESXi is a such kind of Unix-like OS, with same commands.  
But it works on a prorietary VMkernel core.   
There are free and commercial versions (vSphere).  

KVM (Kernel Based VM) is a solution for Linux platforms.  
KVM supports a hardware virtualization technologies Intel VT и AMD-V.  
A SolusVM solution is a control center for the KVM, Xen и OpenVZ managing.  

As for budget, the VMware based solutions are most expensive then others.  
MS Hyper-V just a little more chippest, but don't has a Fault Tolerance.  
And KVM is free, but has no support - only open source comunity can help you.  
