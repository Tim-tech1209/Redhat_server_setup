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