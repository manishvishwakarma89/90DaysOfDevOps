# Linux Architecture – Core Concepts for DevOps
## Goal
Understand how Linux works under the hood. These concepts form the foundation for troubleshooting, performance tuning, and production support as a DevOps engineer.
## 1. Core Components of Linux
Linux follows a layered architecture where each layer has a clear responsibility.
### 1.1 Hardware
Physical components such as CPU, RAM, disk, and network interfaces.
## 1.2 Kernel (The Core of Linux)
The kernel is the heart of the operating system. It directly interacts with hardware and provides services to user-space programs.

Key responsibilities of the kernel:
Process management (CPU scheduling, context switching)
Memory management (RAM allocation, virtual memory)
File system management (ext4, xfs, etc.)
Device management (drivers)
Networking (TCP/IP stack)
Security (permissions, SELinux, AppArmor)
The kernel runs in kernel space, which has full access to hardware.

Check kernel version:
uname -r
