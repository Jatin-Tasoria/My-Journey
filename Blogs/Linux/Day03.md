# Process Management, System Monitoring, Package handling & Basic troubleshooting.
Day 3 is all about diving deeper into linux file system. Today I learned how to manage processes,
monitor system health, how to manage packages and troubleshooting.

## Process management
Processes are the services running in the background and foreground on the system. Understanding them is essential for system performance and stability.

Each process in Linux:
1. Has a Unique PID
2. Owned by specific user
3. Consumes CPU and memory resources
   
### Commands
- ps : List the active processes (running on the current terminal/user).
- ps aux : Lists all the running processed
- top : List the real time processes (Updates after 3 sec).
- pgrep <name> : Finds PIDs of processes by name.
- kill <PID> : To stop a process

### Process states
- Running(R) : Process is either running or ready to run.  
- Sleeping(S) : Interruptible sleep - waiting for event to complete.
- Uninterruptible Sleep(D) : Usually waiting for I/O operations to complete.
- Zombie(Z) : Terminated process waiting for parent to collect exit status.
- Stopped(T) : Process stopped by job control signal or being traced.

- Additional Modifiers:
  - + : Foreground processes
  - s : session leader
  - l : Multi-threaded

---

## System Monitoring
A good system admin always knows how the system is performing.

### Tools and Commands
- top : Real time CPU and memory usage.
- htop : Interactive process viewer
- free -h : Check RAM usage
- df -h : Disk usage
- vmstat : Virtual memory status
- iostat : Disk I/O usage


---

## Package Handling
A package is a group of files that make up a software application.

### Package management tools
- yum
- dnf
- rpm
- apt
  
### Commands
- yum install <Package name>
- yum remove <Package name>   
- yum update <Package name>
- yum check-update

---

## working with systemctl services
System conrol command is a crucial utility that use systemd as init system.

### Commands
- systemctl status <service-name>
- systemctl start <service-name>
- systemctl stop <service-name>
- systemctl restart <service-name>
- systemctl reload <service-name>
- systemctl enable <service-name>
- systemctl disable <service-name>

---

## Troubleshooting
Troubleshooting steps

- Checking service failures with systemctl status
- Reviewing logs using journalctl
- Identifying high resource usage
- Restarting frozen or failed services
- Clearing misconfigured services
- Checking disk space issues using df -h
- Monitoring memory leaks with top