



# Ethernet, ARP, Ping, and MAC Address Table – Notes

## Ethernet Frame Payload (Minimum Size)

An Ethernet frame has a **minimum payload size of 46 bytes**.

### Why a Minimum Payload Is Required
- Ethernet requires a **minimum frame size of 64 bytes**
- If the actual data is less than 46 bytes:
  - **Padding** is added to meet the minimum size
- This ensures:
  - Proper **collision detection** (CSMA/CD in legacy Ethernet)
  - Reliable frame transmission

### Ethernet Frame Size Summary
| Field | Size |
|----|----|
| Header | 14 bytes |
| Payload (minimum) | 46 bytes |
| FCS | 4 bytes |
| **Total Minimum Frame Size** | **64 bytes** |

---

## ARP (Address Resolution Protocol)

ARP is used to **map an IP address to a MAC address** within a local network.

### Why ARP Is Needed
- IP communication happens at **Layer 3**
- Ethernet delivery happens at **Layer 2**
- ARP bridges this gap by finding the destination MAC address

---

### ARP Request
- Sent as a **broadcast**
- Destination MAC: `FF:FF:FF:FF:FF:FF`
- Message:  
  > “Who has this IP address? Tell me your MAC address.”

---

### ARP Reply
- Sent as a **unicast**
- Destination MAC: Requester’s MAC
- Contains the MAC address for the requested IP

---

## ARP Table

The **ARP table** stores mappings of:
- IP Address → MAC Address

### Key Points
- Built dynamically using ARP replies
- Entries age out after a certain time
- Reduces unnecessary ARP broadcasts

### Command to View ARP Table
(On a PC)
```bash
arp -a
````

(On a Cisco device)

```bash
show arp
```

---

## Ping

`ping` is used to **test network connectivity** between two devices.

### What Ping Uses

* **ICMP (Internet Control Message Protocol)**

---

### ICMP Echo Request

* Sent by the source device
* Asks: “Are you reachable?”

### ICMP Echo Reply

* Sent by the destination device
* Confirms reachability

### Ping Process (Simplified)

1. ARP resolves destination MAC (if not known)
2. ICMP Echo Request is sent
3. ICMP Echo Reply is received

---

## MAC Address Table (Switch)

The **MAC Address Table** (CAM table) is used by switches to forward frames.

### What the Table Stores

* MAC Address
* Switch Port
* VLAN (if applicable)

---

### MAC Learning Process

1. Frame arrives at a switch port
2. Switch records the **source MAC address**
3. Entry is stored in the MAC address table
4. Future frames are forwarded efficiently

---

### Unknown vs Known Unicast

* **Unknown Unicast**

  * Destination MAC not in table
  * Frame is **flooded** to all ports except source
* **Known Unicast**

  * Destination MAC exists in table
  * Frame forwarded only to the correct port

---

## Key Takeaways

* Ethernet enforces a **minimum frame size**
* ARP resolves **IP → MAC**
* ARP uses **broadcast request + unicast reply**
* Ping uses **ICMP Echo Request/Reply**
* Switches forward frames using the **MAC address table**
* Unknown unicast causes **flooding**
* Known unicast enables **efficient forwarding**

---

## CCNA (200-301) Relevance

This topic directly maps to:

* Ethernet LAN switching
* ARP operation
* ICMP and connectivity testing
* MAC address learning and forwarding behavior




