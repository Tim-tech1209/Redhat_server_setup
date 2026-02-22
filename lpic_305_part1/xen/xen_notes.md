## Summary for all the command in Xen

### Commands for Xen overall
```bash
# connect to your VM console.
xl console
# show Xen boot messages
xl dmesg
# output the VM dump in file
xl dump-core
# show Xen info
xl info
# list all running VM
xl list
# migrate the VM to the other host
xl migrate
# restore the VM from snapshot
xl restore
# save the VM as a snapshot
xl save
# show all the running VM status in realtime
xl top
```

### Commands for VMs
```bash
# create a VM, and add '-c' to connect to the console
xl create
# terminate the VM
xl destry
# pause the VM
xl pause
# reboot the VM
xl reboot
# shutdown the VM
xl shudown
# resume the VM that was stopped
xl unpause
```

### Manage vCPU
```bash
# list all the vCPU info
xl vcpu-list
# configure the vCPU
xl vcpu-set
```

### Confirm and manage block device
```bash
# attch the block device
xl block-attach
# detach the block device
xl block-detach
# list all the block devices
xl block-list
# eject CD-ROM from CD drive
xl cd-eject
# insert CD-ROM into CD drive
xl cd-inject
```

### xen list 's details
| Field Name | Description |
| :--- | :--- |
| Name | domain name |
|ID | domain ID |
| Mem | assigned memory size |
| VCPUs | number of assigned vCPUs |
| State | domain status |
| Time(s) | domain running time in total |

### Values displayed in the "State" field
| Flag | Name | Description |
| :---: | :--- | :--- |
| **r** | **Running** | The domain is currently scheduled and running on a CPU. |
| **b** | **Blocked** | The domain is idle or waiting for an event (e.g., I/O). |
| **p** | **Paused** | The domain has been paused (usually by `xl pause`). |
| **s** | **Shutdown** | The guest OS has initiated a shutdown but hasn't fully exited yet. |
| **c** | **Crashed** | The domain has crashed and is no longer running. |
| **d** | **Dying** | The domain is in the process of being destroyed or cleaned up. |
| **h** | **HVM** | The domain is running as a Hardware-Assisted Virtual Machine. |