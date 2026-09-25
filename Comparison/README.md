# Comparison - Type-1 vs Type-2 Hypervisor

This folder has the comparison graph and result comparison between Proxmox VE (Type-1) and VMware Workstation (Type-2).

## Comparison Table

| | Type-1 (Proxmox VE) | Type-2 (VMware Workstation) |
|---|---|---|
| Total Execution Time | 10.0030s | 10.0008s |
| Total Events | 14548 | 12778 |
| Events per Second | 1453.98 | 1277.56 |
| Average Latency | 0.69 ms | 0.78 ms |

## Graph

![Comparison graph](comparison-graph.png)

## Which is Better

In this test, Proxmox VE (Type-1) gave a higher events per second (1453.98) than VMware Workstation (Type-2) (1277.56), and also had lower average latency (0.69 ms vs 0.78 ms). So for this Sysbench CPU test, Proxmox VE performed better than VMware Workstation.

This makes sense because Proxmox VE is a Type-1 hypervisor that runs directly on the hardware, while VMware Workstation is a Type-2 hypervisor that runs on top of a host operating system, which adds extra overhead.

Note: Both VMs had the same configuration (2 vCPU, 2 GB RAM, 20 GB disk), so this is a fair comparison for this one test.
