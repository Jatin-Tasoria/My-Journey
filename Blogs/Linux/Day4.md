 # Linux Networking
A network is a group of interconnected computers.
And Networking is working and handling networks.

## Basic concepts
**IP address**
AN IP address is a unique identifier for a device on a network.

**IPv4**
32-bit addresses like 192.168.1.10

**Public vs Private IP** 
Private (LAN) vs Public (Internet)

**Subnet Mask**
Defines network & host portion (e.g., 255.255.255.0)

**Gateway**
The device that connects your system to external networks

**DNS**
Converts domain names (google.com) → IP addresses

### Essential Commands
1. ifconfig : To view and configure network interface
2. ping <website/IP address> : To check whether a system is able to communicate with another system ver the network
3. hostnamectl : View/modify system hostname 
4. wget <URL> : Used to retrieve content from web server
5. curl <URL> : Used to transfer data using various protocols
6. nmcli : networkManager controller

---

## Hostname & DNS
**Important Files:**
- /etc/hosts → static hostname entries
- /etc/resolv.conf → DNS servers

### Commands:
1. dig <website>
2. nslookup <website>

---

## Networking Service Management
Control networking services and connections.

### Commands:
1. systemctl restart NetworkManager
2. nmcli device status
3. nmcli connection show

---

## Firewall Basics
Firewalls are crucial for Linux security and understanding AWS Security Groups.

### Commands:
1. firewall-cmd --state
2. firewall-cmd --list-all
3. firewall-cmd --add-port=80/tcp --permanent
4. firewall-cmd --reload

---