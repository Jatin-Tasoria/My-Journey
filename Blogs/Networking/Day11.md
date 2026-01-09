#  AWS VPC – Complete Beginner to Cloud-Ready Guide

A **VPC (Virtual Private Cloud)** is the **foundation of everything in AWS**.
Before launching EC2, databases, or applications, AWS requires you to design a **secure network**.

In simple terms:

> **AWS VPC = Your own private data center network inside Amazon Web Services**

---

##  What Is AWS VPC?

A **VPC** is a **logically isolated virtual network** in AWS where you can:

* Define IP address ranges
* Create subnets
* Control routing
* Secure traffic

Each VPC is **isolated by default**.

---

### Real-World Analogy

| Real World      | AWS              |
| --------------- | ---------------- |
| Office building | VPC              |
| Floors          | Subnets          |
| Main gate       | Internet Gateway |
| Security guard  | Security Group   |
| Internal router | Route Table      |

---

## CIDR Block – IP Address Range

When creating a VPC, you assign a **CIDR block**.

Example:

```
10.0.0.0/16
```

Meaning:

* Total IPs: ~65,000
* Private IP range
* Used inside AWS

📌 AWS allows:

* `/16` to `/28` CIDR size

---

## Subnets – Dividing the Network

A **subnet** is a **smaller network inside a VPC**.

Example:

```
VPC: 10.0.0.0/16

Public Subnet:  10.0.1.0/24
Private Subnet: 10.0.2.0/24
```

---

### Public Subnet

A subnet is **public** if:

* It has a route to **Internet Gateway**
* Instances can access the internet

Used for:

* Bastion hosts
* NAT Gateway
* Load Balancers

---

### Private Subnet

A subnet is **private** if:

* No direct route to Internet Gateway
* Internet access only via NAT

Used for:

* Application servers
* Databases

---

##  Internet Gateway (IGW)

An **Internet Gateway** allows:

* Internet → VPC
* VPC → Internet

**Important**:

* One IGW per VPC
* Stateless
* Required for public subnets

Without IGW → **no internet access at all**

---

##  NAT Gateway – Internet for Private Subnets

Private subnets **cannot access the internet directly**.

### Why NAT Gateway?

* Allows **outbound internet access**
* Blocks **inbound internet access**

### Traffic Flow

```
Private EC2 → NAT Gateway → Internet
```

NAT Gateway:

* Lives in **public subnet**
* Uses Elastic IP
* Managed by AWS

---

## Security Groups vs NACLs (Quick View)

### Security Groups

* Instance level
* Stateful
* Allow rules only

### Network ACLs

* Subnet level
* Stateless
* Allow & deny rules

---

## 8️⃣ DNS & DHCP in AWS VPC

AWS automatically provides:

* DNS resolution
* DHCP service

Each EC2 gets:

* Private IP
* DNS
* Gateway

> You **never configure DHCP manually** in AWS.

---

### Traffic Explanation

| Source      | Destination | Path        |
| ----------- | ----------- | ----------- |
| Public EC2  | Internet    | IGW         |
| Private EC2 | Internet    | NAT Gateway |
| Internet    | Private EC2 | ❌ Blocked   |

---