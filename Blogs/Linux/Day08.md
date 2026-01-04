# Security & Hardening
It is the **final day** of the linux. From tomorrow, I will either start **Advance Networking** Or **AWS** Or will add some **Missing Topics**.

## Why security matters (In AWS)
When you launch an EC2 instance on Amazon Web Services, AWS gives you:
- An OS (Amazon Linux / RHEL / Ubuntu)
- A key pair
- A security group

From that point onward, Linux security is your responsibility:
- SSH access
- Firewall rules
- Users & permissions
- SELinux (enterprise environments)

---

## SSH Security
**SSH** or **Secure Shell** allows secure remote login into Linux Servers.

### Password vs Key-Based logins
| Method   | Security | AWS Usage  |
| -------- | -------- | ---------- |
| Password | Weak     | Not used   |
| SSH Keys | Strong   | Default    |

### Commands
- SSH Setup
```bash
ssh user@ip
```
- Key generation
```bash
ssh-keygen
```
>The keygen command will create two keys : Public and Private
- Copy Public Key to Server
```bash
ssh-copy-id user@ip
```
- Login without password
```bash
ssh user@ip
```

---

## SSH Hardening
Hardening refers to allowing only the users to have access to the **SSH login** and not even **root**.

You need to edit file
```bash
etc/shh/sshd_config
```

>Change these settings
- PermitRootLogin no
- PasswordAuthentication no

>Add this for additional Security
- AuthenticationMethods publickey
- AllowUsers username

**After this restart the SSH service**
- systemctl restart ssh **OR** sshd

---

## FirewallD

### Concepts
| Linux FirewallD | AWS               |
| --------------- | ----------------- |
| Zones           | Security Groups   |
| Services        | Allowed protocols |
| Ports           | Inbound rules     |

### Useful Command
- firewall-cmd --get-active-zones
- firewall-cmd --list-all

**Allow SSH**
- firewall-cmd --add-service=ssh --permanent

**Apply Changes**
- firewall-cmd --reload

**Verify open ports**
- ss -tulnp

---

## SeLinux 
It stands for Security Enhanced Linux
It controls what a process is allowed to do, even if permissions allow it.

### SeLinux Modes
| Mode       | Description           |
| ---------- | --------------------- |
| Enforcing  | Blocks violations     |
| Permissive | Logs only             |
| Disabled   | Off (not recommended) |

### Commands
**Check modes**
- sestatus
- getenforce

**Change Modes(Temporary)**
- setenforce 0
- # Security & Hardening
It is the **final day** of the linux. From tomorrow, I will either start **Advance Networking** Or **AWS**.

## Why security matters (In AWS)
When you launch an EC2 instance on Amazon Web Services, AWS gives you:
- An OS (Amazon Linux / RHEL / Ubuntu)
- A key pair
- A security group

From that point onward, Linux security is your responsibility:
- SSH access
- Firewall rules
- Users & permissions
- SELinux (enterprise environments)

---

## SSH Security
**SSH** or **Secure Shell** allows secure remote login into Linux Servers.

### Password vs Key-Based logins
| Method   | Security | AWS Usage  |
| -------- | -------- | ---------- |
| Password | Weak     | Not used   |
| SSH Keys | Strong   | Default    |

### Commands
- SSH Setup
```bash
ssh user@ip
```
- Key generation
```bash
ssh-keygen
```
>The keygen command will create two keys : Public and Private
- Copy Public Key to Server
```bash
ssh-copy-id user@ip
```
- Login without password
```bash
ssh user@ip
```

---

## SSH Hardening
Hardening refers to allowing only the users to have access to the **SSH login** and not even **root**.

You need to edit file
```bash
etc/shh/sshd_config
```

>Change these settings
- PermitRootLogin no
- PasswordAuthentication no

>Add this for additional Security
- AuthenticationMethods publickey
- AllowUsers username

**After this restart the SSH service**
- systemctl restart ssh **OR** sshd

---

## FirewallD

### Concepts
| Linux FirewallD | AWS               |
| --------------- | ----------------- |
| Zones           | Security Groups   |
| Services        | Allowed protocols |
| Ports           | Inbound rules     |

### Useful Command
- firewall-cmd --get-active-zones
- firewall-cmd --list-all

**Allow SSH**
- firewall-cmd --add-service=ssh --permanent

**Apply Changes**
- firewall-cmd --reload

**Verify open ports**
- ss -tulnp

---

## SeLinux 
It stands for Security Enhanced Linux
It controls what a process is allowed to do, even if permissions allow it.

### SeLinux Modes
| Mode       | Description           |
| ---------- | --------------------- |
| Enforcing  | Blocks violations     |
| Permissive | Logs only             |
| Disabled   | Off (not recommended) |

### Commands
**Check modes**
- sestatus
- getenforce

**Change Modes(Temporary)**
- setenforce 0
- setenforce 1

> 0 for permissive & 1 for enforcing

**Permanent config**
- etc/seliunx/config

---