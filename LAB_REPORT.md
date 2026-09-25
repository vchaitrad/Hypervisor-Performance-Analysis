# Lab Report

## Experiment Name

Performance Analysis of Type-1 and Type-2 Hypervisors

## Aim

To create the same Ubuntu virtual machine on a Type-1 hypervisor (Proxmox VE) and a Type-2 hypervisor (VMware Workstation), run a Sysbench CPU benchmark on both, and compare their performance.

## Requirements

- Proxmox VE server (Type-1 hypervisor)
- VMware Workstation (Type-2 hypervisor)
- Ubuntu ISO
- Sysbench benchmarking tool
- Internet connection

## VM Configuration

- OS: Ubuntu
- CPU: 2 vCPU
- RAM: 2 GB
- Disk: 20 GB
- Benchmark tool: Sysbench

Sysbench command used:

```bash
sysbench cpu --cpu-max-prime=20000 run
```

## Procedure

### Type-1: Proxmox VE

1. Logged in to Proxmox VE from the browser.
2. Created a new VM with the settings above.
3. Installed Ubuntu on the VM.
4. Checked system details using `hostnamectl`, `lscpu`, `free -h`, `df -h` and `top`.
5. Installed Sysbench and ran the CPU benchmark.
6. Noted down the results.

### Type-2: VMware Workstation

1. Opened VMware Workstation and created a new VM with the settings above.
2. Installed Ubuntu on the VM.
3. Checked system details using `hostnamectl`, `lscpu`, `free -h`, `df -h` and `top`.
4. Installed Sysbench and ran the CPU benchmark.
5. Noted down the results.

## Results

### Type-1: Proxmox VE

- Total Execution Time: 10.0030s
- Total Events: 14548
- Events per Second: 1453.98
- Average Latency: 0.69 ms

### Type-2: VMware Workstation

- Total Execution Time: 10.0008s
- Total Events: 12778
- Events per Second: 1277.56
- Average Latency: 0.78 ms

## Comparison

| | Type-1 (Proxmox VE) | Type-2 (VMware Workstation) |
|---|---|---|
| Events per Second | 1453.98 | 1277.56 |
| Average Latency | 0.69 ms | 0.78 ms |

## Result / Conclusion

Proxmox VE (Type-1) gave a higher events per second and lower average latency than VMware Workstation (Type-2) in this test. Both VMs had the same configuration, so Proxmox VE performed better in this experiment. This is because Type-1 hypervisors run directly on the hardware, while Type-2 hypervisors run on top of a host operating system, which adds some overhead.
