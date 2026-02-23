### /etc/xen/xl.cfg Configuration Guide

| Field Name | Description |
| :--- | :--- |
| bootloader="program" | Specify the program that finds the kernel and initrd. |
| builder=generic | Specify VM type, eg. PV=generic(default), or hvm. |
| disk=['disk def', 'disk def', ...] | Specify the disk devices that is allocated to the VM, like 'disk = [ 'format=raw, vdev=xvda, access=rw, target=/var/lib/xen/images/ubuntu.img' ]'|
| kernel="kernel image file" | Specify the absolute path to kernel image file, like 'kernel = "/boot/vmlinuz-5.15.0-generic"'|
| memory=memory size | Specify memory size(MB). |
| name="VM name"| Specify the name of the VM |
| ramdisk="RAM disk file"| Specify the abosolute path to RAM disk file, like 'ramdisk = "/boot/initrd.img-5.15.0-generic"' |
| boot="c/d/n" | Specify the boot device. c=hard_disk, d=CD_ROM,n=network |
| root="device_name access_permission" | Specify the root device, like 'root = "/dev/xvda1"'|
| uuid="UUID value" | Specify the UUID of the VM (for domain identification,128bit) |
| vcpus=the number of vCPU | Specify the the number of vCPU |
| on_crash='action' | Specify the action when Domain-U crashed |
| on_poweroff='action' | Specify the action when 'xm shutdown' executed or Domain-U shutted down |
| on_reboot='action' | Specify the action when 'xm reboot' executed or Domain-U get rebooted |
| vif=['network def','network def'...] | Specify MAC address, VLAN, bridge, IP address of the virtual network |

### Xen DomU Configuration File Example (.cfg)
#### --- Basic Identity Definitions ---
name   = "ubuntu_web"          # Unique name for the virtual machine
uuid   = "550e8400-e29b-41d4-a716-446655440000" # (Optional) Universally Unique Identifier

#### --- Resource Allocation ---
vcpus  = 2                     # Corresponds to 'vcpus': Allocates 2 Virtual CPUs
memory = 2048                  # Corresponds to 'memory': Allocates 2048MB (2GB) of RAM
maxmem = 4096                  # (Optional) Maximum memory the VM can dynamically scale to

#### --- Bootloader & Kernel Settings ---
kernel = "/boot/vmlinuz-5.4.0-generic" # Path to the kernel image located in Dom0
ramdisk = "/boot/initrd.img-5.4.0-generic" # Corresponds to 'ramdisk': Path to the Initial RAM Disk
root   = "/dev/xvda1 ro"       # Specifies the root device for the kernel
extra  = "console=hvc0"        # Extra kernel parameters (e.g., for terminal display)

#### --- Storage Definitions ---
#### Corresponds to 'disk': Defines virtual disk mappings
#### Format: [ 'source_path, virtual_device_name, read_write_mode' ]
disk   = [ 
    'file:/var/lib/xen/images/ubuntu_web.img,xvda,w', 
    'file:/var/lib/xen/images/data.img,xvdb,w' 
]

#### --- Network Definitions ---
vif    = [ 'bridge=xenbr0' ]   # Virtual Interface; bridges to the 'xenbr0' bridge on Dom0