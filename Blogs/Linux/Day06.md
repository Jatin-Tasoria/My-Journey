# Logs, Boot and Troubleshooting

## Logs
Linux stores systems and service information in log files. These logs helps admins to understand **what happened, when it happened** and **why it happened**.

### Important log locations
```
/var/log/          → Main log directory
/var/log/messages  → General system messages
/var/log/secure    → Authentication & SSH logs
/var/log/cron      → Cron job activity
/var/log/dnf.log   → Package installation logs
```

## journalctl
Modern Linux distributions (RHEL, Ubuntu, AWS EC2) use systemd, which stores logs in a centralized journal.

### Commands
- journalctl : View all logs
- journalctl -xe : Recent logs with explanations
- journalctl -u sshd : Logs for a specific service
- journalctl --since "1 hour ago"
- journalctl -p err : Error-level logs
- journalctl -b : Logs since last boot

---

## Service Troubleshooting with systemctl
Most Linux services are managed using systemctl.

### Commands
- systemctl status service_name
- systemctl restart service_name
- systemctl enable service_name
- systemctl disable service_name

---

## Boot and Kernel Troubleshooting

Linux Boot Sequence
```
BIOS → GRUB → Kernel → systemd → Services
```
### Commands
- dmesg
- dmesg | tail
- uptime

---

## Disk & Memory Issue Detection
Disk and memory problems are very common on servers.

### Commands
- df -h        # Disk usage
- du -sh /*    # Directory sizes
- free -h      # Memory usage
- top          # Real-time process monitoring

---