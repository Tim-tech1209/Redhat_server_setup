## XenStore
XenStore is a shared database of configuration information regarding currently running domains.

The information is stored using a hierarchical namespace, and you can verify the contents using the xenstore-ls command. It is managed by a daemon called xenstored located in Domain-0.

Through XenStore, you can monitor the configuration information of active virtual machines that changes dynamically during execution, such as virtual CPUs (vCPUs), memory, and devices.

## Quick Command Reference
If you are experimenting with XenStore, here are the most common commands you will use:
* xenstore-ls: Lists the entire hierarchy (or a specific path).
* xenstore-read <path>: Reads the value of a specific key.
* xenstore-write <path> <value>: Manually updates a value (use with caution!).
* xenstore-watch: Monitors a path for real-time changes.

## Configuring Dom0 Memory Limits
In Xen, the boot-time option dom0_mem, which restricts the memory allocated to the management domain (Domain-0), is defined within the bootloader configuration files, such as grub.conf (GRUB1) or grub.cfg (GRUB2).

### Bootloader configuration file for the Xen kernel
| GRUB Version | Path & File_name |
| :--- | :--- |
| GRUB1 | /boot/grub/grub.conf |
| GRUB2 | /boot/grub/grub.cfg > edit with 'grub-mkconfig' to modify /etc/default/grub |