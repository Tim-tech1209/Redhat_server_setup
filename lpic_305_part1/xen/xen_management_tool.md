## Xen Management Toolstacks
#### In Xen 4.x, there are three main types of toolstacks (management tools), with xl being the default. In addition to xl, libvirt and XAPI are also available.

#### The relationship between the "Toolstack," "Primary Daemon," and "CLI Command" is as follows:
| Toolstack | Primary Daemon | CLI Command |
| :--- | :--- | :--- |
| xl | xenstored & xenconsoled | xl |
| libvirt | libvirtd | virsh |
| XAPI | xapi | xe |

### **xl (xl command)**
#### xl is the default toolstack for Xen used from version 4.1 onwards. It involves the xenstored and xenconsoled daemons.

#### The previous toolstack for Xen 3.x, xend (xm), was maintained for compatibility in Xen 4.1 through 4.4 but was officially deprecated in Xen 4.5. The xl command was designed with xm compatibility in mind; with a few exceptions, almost all the same commands can be used.

### **libvirt (virsh command)**
#### libvirt is an open-source, unified management framework for virtualization in general, powered by the libvirtd daemon. It can control various virtualization software beyond Xen, including KVM, QEMU, OpenVZ, and VirtualBox.

#### Beyond the virsh CLI, other tools are available within this ecosystem:
* virt-manager: A GUI tool for managing virtual machines.
* virt-install: A command-line tool for creating new virtual machines.

### **XAPI (xe command)**
#### XAPI (The Xen Project Management API) is the standard management API used in Citrix Hypervisor (formerly XenServer)—a virtualization product based on Xen with added enterprise management features. It accesses management components via the xapi daemon located in Domain-0 (the management VM).

#### XAPI is a high-performance toolstack designed for enterprise use, capable of managing large-scale systems where multiple Xen hosts are operational. While Citrix Hypervisor provides a GUI called XenCenter, the xe command allows for detailed management via the CLI.

#### Furthermore, XAPI can be installed and operated using the xe command on standard Linux distributions, not just on Citrix Hypervisor.



