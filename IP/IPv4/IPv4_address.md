



# IPv4 Addressing – Fundamentals

## Overview
An **IPv4 address** is a **32-bit logical address** used to uniquely identify a device on an IP network.  
It operates at **Layer 3 (Network Layer)** of the OSI model.

IPv4 addresses are written in **dotted-decimal format**, divided into **four octets**.

Example:
```

192.168.1.1

```

---

## IPv4 Address Structure
An IPv4 address consists of two parts:
- **Network Portion** – Identifies the network
- **Host Portion** – Identifies a device within the network

The division is determined by the **subnet mask**.

---

## Binary Representation
Each octet contains **8 bits**:
```

192  . 168  .  1  .  1
11000000.10101000.00000001.00000001

```

---

## IPv4 Address Classes (Classful Addressing)

| Class | Range | Default Subnet Mask | Usage |
|----|----|----|----|
| A | 1.0.0.0 – 126.255.255.255 | 255.0.0.0 | Large networks |
| B | 128.0.0.0 – 191.255.255.255 | 255.255.0.0 | Medium networks |
| C | 192.0.0.0 – 223.255.255.255 | 255.255.255.0 | Small networks |
| D | 224.0.0.0 – 239.255.255.255 | N/A | Multicast |
| E | 240.0.0.0 – 255.255.255.255 | N/A | Experimental |

---

## Private IPv4 Address Ranges
Private addresses are **not routable on the Internet**.

| Class | Private Range |
|----|----|
| A | 10.0.0.0 – 10.255.255.255 |
| B | 172.16.0.0 – 172.31.255.255 |
| C | 192.168.0.0 – 192.168.255.255 |

---

## Subnet Mask
A **subnet mask** identifies the network and host portions of an IP address.

Example:
```

IP Address:   192.168.1.10
Subnet Mask:  255.255.255.0

```

Network:
```

192.168.1.0

```



CIDR Notation
CIDR (Classless Inter-Domain Routing) uses **prefix length** notation.

Example:
```

192.168.1.10/24

```

- `/24` → 24 bits for network
- Remaining bits → host addresses



Network & Broadcast Addresses

For any subnet:
- Network Address → First address (all host bits = 0)
- Broadcast Address → Last address (all host bits = 1)

Example:
```

Network:   192.168.1.0
Broadcast: 192.168.1.255

```

These addresses cannot be assigned to hosts.



Usable Host Range
```

192.168.1.1  →  192.168.1.254

```

Total hosts:
```

2^n - 2

```
(where `n` = number of host bits)

---

## Special IPv4 Addresses

| Address | Purpose |
|----|----|
| 127.0.0.1 | Loopback |
| 0.0.0.0 | Unspecified / default route |
| 255.255.255.255 | Limited broadcast |

---

## IPv4 Address Types
- **Unicast** – One-to-one communication
- **Broadcast** – One-to-all (within subnet)
- **Multicast** – One-to-many (Class D)

---

## Key Takeaways
- IPv4 is a 32-bit address
- Subnet masks define network boundaries
- CIDR allows flexible subnetting
- Network & broadcast addresses are reserved
- Private IPs are used inside local networks

---

## CCNA (200-301) Relevance
This topic is essential for:
- IP addressing and subnetting
- Routing decisions
- Network design and troubleshooting



