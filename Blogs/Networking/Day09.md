# Introduction

>Note: Before Starting Networking Start with Linux
[Linux](../Linux/README.md)

---

## Subnetting
Dividing a large network int smaller network.

Why do we do it:
- Better Security
- Efficient IP usage
- Traffic Isolation
- Cloud Design

### Key Terms
| Term              | Meaning                             |
| ----------------- | ----------------------------------- |
| Network Address   | First IP of subnet (not usable)     |
| Broadcast Address | Last IP (not usable)                |
| Usable IPs        | IPs between network & broadcast     |
| Subnet Mask       | Defines network vs host bits        |
| CIDR              | Slash notation (`/24`, `/16`, etc.) |

Example: 192.168.1.0/24
/24 → 24 bits for network
Remaining bits → hosts

Calculation:
Total IPs = 2^(32-24) = 256
Usable = 256 − 2 = 254
| Item      | Value         |
| --------- | ------------- |
| Network   | 192.168.1.0   |
| Broadcast | 192.168.1.255 |
| First IP  | 192.168.1.1   |
| Last IP   | 192.168.1.254 |

Why `/24`,`/25` matters
| CIDR | Total IPs | Usable |
| ---- | --------- | ------ |
| /24  | 256       | 254    |
| /25  | 128       | 126    |
| /26  | 64        | 62     |
| /27  | 32        | 30     |
| /28  | 16        | 14     |

---

## CIDR
Tells how many host you can deploy.
Formula:
```
Hosts = 2^(32 − CIDR) − 2
```

Example:
/24 → 32−24 = 8
2^8 = 256
Usable = 254

---

## Routing
Decides where the Packets should go?

Systems check routes **top to bottom**

Example:
```
default via 192.168.1.1
```
>If no specific route matches → traffic goes to default gateway.

---

## Ports and Protocol
| Service | Port |
| ------- | ---- |
| SSH     | 22   |
| HTTP    | 80   |
| HTTPS   | 443  |
| DNS     | 53   |

---