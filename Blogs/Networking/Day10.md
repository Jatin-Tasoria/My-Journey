# NAT, DNS, DHCP & AWS Mapping
This is the final networking day before starting AWS.

## NAT
Network Address Translation

### Why NAT Exists
Private IP addresses (RFC 1918):
- 10.0.0.0/8
- 172.16.0.0/12
- 192.168.0.0/16

These are IP addresses reserved for private network.
These cannot be routed on the public internet.

### How NAT Works
NAT translates:
```
Private IP  →  Public IP
```
This translation allows:
- Outbound internet access
- Controlled inbound access (if required)

### Types of NAT
- SNAT (Source NAT)
Changes source IP
Used when internal systems access the internet

- DNAT (Destination NAT)
Changes destination IP
Used for port forwarding and incoming traffic

- MASQUERADE (Linux)
Dynamic SNAT
Used when public IP changes frequently (home internet)

- AWS NAT Gateway
Managed SNAT service
Allows private subnet → internet
Blocks internet → private subnet

### Linux VS AWS Mapping
| Linux Networking  | AWS              |
| ----------------- | ---------------- |
| NAT               | NAT Gateway      |
| Public interface  | Public subnet    |
| Private interface | Private subnet   |
| Default route     | Route Table      |
| Internet access   | Internet Gateway |


---

## DNS
Domain Name System
Resolves Names to Numbers
Specifically Domain names to IP addresses

### What Happens Internally
1. User enters google.com
2. System checks /etc/hosts
3. If not found → queries DNS server(Resolver)
4. DNS server returns IP
5. System connects to that IP

> The Resolver is basically ISP(Internet Service Provider)

### AWS DNS Mapping
- AWS provides built-in DNS
- VPC has an AmazonProvidedDNS
- Route 53 (used later) is AWS’s DNS service
---

## DHCP
Dynamic Host Configuration Protocol
Automatically assigns network settings to devices

It provides:
- IP address
- Subnet mask
- Default gateway
- DNS server(s)
- Lease time

Without DHCP, every device would need manual IP configuration—slow and error-prone.

### AWS DHCP Mapping
- AWS manages DHCP automatically
- EC2 instances receive:
  - Private IP
  - Gateway
  - DNS
- No manual DHCP configuration required

---

## Key Understanding
| Concept          | Meaning                 |
| ---------------- | ----------------------- |
| Temporary config | `ip`, `nmcli`           |
| Permanent config | Config files            |
| NetworkManager   | Modern Linux networking |
| network-scripts  | Legacy (RHEL-based)     |

---