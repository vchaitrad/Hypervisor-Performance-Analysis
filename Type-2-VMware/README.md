# Type-2 Hypervisor - VMware Workstation

This folder has the screenshots and details of the VMware Workstation part of my hypervisor performance experiment.

## Requirements

- A PC with VMware Workstation installed
- Ubuntu ISO file
- Internet connection (for installing Sysbench inside the VM)

## Machine Specification (VM)

- OS: Ubuntu
- CPU: 2 vCPU
- RAM: 2 GB
- Disk: 20 GB
- Network Adapter: NAT

## Procedure

1. Opened VMware Workstation and clicked Create a New Virtual Machine.
2. Selected Typical (recommended) configuration.
3. Selected Installer disc image file (iso) and browsed to the Ubuntu ISO.
4. Guest OS: Linux, Ubuntu 64-bit.
5. Name: `CC-Experiment1-Type2`.
6. Disk: 20 GB.
7. In Customize Hardware, set:
   - Memory: 2048 MB (2 GB)
   - Processors: 1 processor, 2 cores (2 vCPU)
   - Network Adapter: NAT
8. Powered on the VM and installed Ubuntu (computer name `cc-type2-vm`).
9. Restarted and logged in.
10. Checked the machine using `hostnamectl`, `lscpu`, `free -h`, `df -h` and `top`.
11. Installed Sysbench and ran the CPU benchmark.
12. Checked the hardware settings under VM, then Settings.
13. Shut down the VM using `sudo poweroff`.

## Commands Used

```bash
sudo apt update
sudo apt install sysbench -y
sysbench --version
sysbench cpu --cpu-max-prime=20000 run
```

```bash
hostnamectl
lscpu
free -h
df -h
top
sudo poweroff
```

## Screenshots

## Screenshots

## Screenshots

- `lspu.jpg`, `lspu1.jpg` - `lscpu` output (CPU details)
- `free -h.jpg` - `free -h` output (memory usage)
- `Sysbench.jpg`, `sysbenchjpg.jpg` - Sysbench CPU test result

## Result

Sysbench CPU test - `sysbench cpu --cpu-max-prime=20000 run`

CPU speed:
- Events per Second: 1277.56

General statistics:
- Total Time: 10.0008s
- Total Number of Events: 12778

Latency (ms):
- Minimum: 0.65
- Average: 0.78
- Maximum: 7.56
- 95th Percentile: 1.39
