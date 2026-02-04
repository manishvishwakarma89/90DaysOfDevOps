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
## 1.3 User Space

User space is where applications and user processes run. Programs here do not access hardware directly; they use system calls to interact with the kernel.

User space components:

Applications (nginx, docker, mysql, python)

Shells (bash, zsh)

System utilities (ls, ps, top)

##  1.4 Init System (systemd)
The init system is the first process started by the kernel (PID 1).
Modern Linux distributions use systemd as the init system.
# 2. Process Management in Linux
A process is an instance of a running program.
## 2.1 Process Creation
fork: A new process is created using fork()
exec: The new process may replace its memory using exec()
PID: Every process has a unique PID (Process ID)
Processes form a parent-child hierarchy
PID 1 is always the init/systemd process.
## 2.2 Process Types
Foreground process – runs in the terminal
Background process – runs behind the terminal
Daemon process – long-running service (nginx, sshd)
## 2.3 Process States
### State	Meaning
R	Running;
S	Sleeping;
D	Uninterruptible sleep;
T	Stopped;
Z	Zombie;
## 2.4 Viewing and Managing Processes
Common commands:
ps -ef
ps aux
top
htop
Kill processes:
kill PID
kill -9 PID
pkill nginx

# 3. systemd – Service and System Manager
## 3.1 What is systemd?
systemd is the modern init system and service manager used by most Linux distributions.

It is responsible for:
Booting the system
Starting and stopping services
Managing dependencies
Logging
Handling system states
systemd always runs as PID 1.
Check:
ps -p 1



