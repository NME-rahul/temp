# Virtualization

* In the old days if you want to run three different softwares that requires three different operating system then you have to purchase three different machines running three OS and top of them softwares but virtalization makes possible to run all three OS to run on the same physical machine.
* Virtualization helps to create three different virtual(not physical) machine, the software that creates those virtual machine is called hypervisor (in general, Hypervisor sits on top of the physical hardware and create the virtual machine by slicing the resources).
* Important to note is each virtual machine on a host(physical hardware) is an independent machine meaning they act like seprate physical machine.


1. **The Host:** The actual physcial hardware(the server, desktop, or laptop).
2. **Hypervisor:** The software that manages and allocates resources(also called Virtual Machine Manager or VMM).
3. **The Guest(VM):** The virtual enviornement that runs its own OS and apps as if it were on its own dedicated physical machine.


## Approaches of Virtualization

1. Full virtualization or traditional hypervisors: In Full virtualzation, virtual machines is completly unaware of virtualization and think it is running on real hardware.
2. Emulators: They allow to run application written for completely different hardware, it actually simulates the target hardware for OS to run. The common examples are gamming simulators.
3. Paravirtualization: unlike full virtualization the guest OS knows the about the hypervisor. the guest OS is modified to work in co-operation with the VMM to optimize performance.
4. Containers: It is not virtualization but provides virtualization like feature by seggregating application from the OS. All containers shares the same kernel of the OS but live in isolated space. Docker, and kubernets are the examples of it.
5. Programming-environment virtualization: 


## Full virtualization
* Each guest is provided with the virtual copy of host. There are different type of hypervisors, `type-0`, `type-1`, and `type-2` hypervisor.

### 1. Type-0 hypervisor(Hardware-Embedded):

Type-0 is a hardware-based solution where the virtualization logic is implemented directly in the firmware or hardware, rather than as software layer on top it. It uses hardwae r partiononing to divide a single physical machine into multiple independent system. The hardware itself manages the sepration. Performance is near-native since the ypervisor is essentially built into the motherboard or CPU logc, there is almost zero software overhead. common examples are LPARs or high-end RISC systems.


### 2. Type-1 hypervisor(Bare-Metal): 

<div align="center">
  <img width="595" height="381" alt="image" src="https://github.com/user-attachments/assets/4973aa06-b375-4a94-9c9b-860008513129" />
</div>

### 3. Type-2 hypervisor(Hosted Hypervisor): 

Hypervisor itself is a process on the host operating system. These type of hypervisors are the application that run on the top of a convetional Operating system(like Windows, MacOS, or Linux). Performace is lower then Type-0 and Type-1, every request from VM has to go through the hypervisor $rightarrow$ Host OS $rightarrow$ Hardware. It is used for software testing and developers who need to run a differnt OS for specifc tools without rebooting their main computer. Common examples are Oracle VirtualBox, Vmware Wokstation/Fusion, and Parallels desktop.



<div align="center">
  <img width="553" height="423" alt="image" src="https://github.com/user-attachments/assets/62acdb97-91ce-4c91-a09a-9f3096348add" />
</div>
