### /etc/xen/xl.cfg Configuration Guide

| Field Name | Description |
| :--- | :--- |
| bootloader="program" | Specify the program that finds the kernel and initrd. |
| builder=generic | Specify VM type, eg. PV=generic(default), or hvm. |
| disk=['disk def', 'disk def', ...] | Specify the disk devices that is allocated to the VM. |
| kernel="kernel image file" | Specify the absolute path to kernel image file, like 'kernel = "/boot/vmlinuz-5.15.0-generic"'|
| memory=memory size | Specify memory size(MB). |
| name="VM name"| Specify the name of the VM |
| ramdisk="RAM disk file"| Specify the abosolute path to RAM disk file, like 'ramdisk = "/boot/initrd.img-5.15.0-generic"' |
| boot="c/d/n" | Specify the boot device. c=hard_disk, d=CD_ROM,n=network |
| root="device_name access_permission" | Specify the root device |
| uuid="UUID value" | Specify the UUID of the VM (for domain identification,128bit) |
| vcpus=the number of vCPU | Specify the the number of vCPU |
| on_crash='action' | Specify the action when Domain-U crashed |
| on_poweroff='action' | Specify the action when 'xm shutdown' executed or Domain-U shutted down |
| on_reboot='action' | Specify the action when 'xm reboot' executed or Domain-U get rebooted |
| vif=['network def','network def'...] | Specify MAC address, VLAN, bridge, IP address of the virtual network |