# Ethernet Frames and Ethernet Switching (MAC Address Based)

## Overview
This note covers the fundamentals of **Ethernet frames** and **Ethernet switching**, with a focus on how switches use **MAC addresses** and the **MAC address table** to forward traffic efficiently within a Local Area Network (LAN).

These concepts are core topics for **CCNA (200-301)** and essential for understanding Layer 2 switching.

---

## Ethernet Frame
An **Ethernet frame** is the basic unit of data transmission at **Layer 2 (Data Link Layer)** of the OSI model.

### Ethernet Frame Components
- **Destination MAC Address** – MAC address of the receiving device
- **Source MAC Address** – MAC address of the sending device
- **Type / Length** – Indicates the upper-layer protocol
- **Payload (Data)** – Encapsulated Layer 3 data
- **FCS (Frame Check Sequence)** – Used for error detection

---

## Ethernet Switching
Ethernet switching is the process by which a **switch forwards frames** based on **MAC addresses** rather than IP addresses.

Switches operate at **Layer 2** and make forwarding decisions using a **MAC address table**.

---

## MAC Address Table
The **MAC address table** (also called CAM table) stores mappings between:
- **MAC Address**
- **Switch Port**
- **VLAN (if applicable)**

### MAC Address Learning Process
1. A frame arrives on a switch port
2. The switch records the **source MAC address** and associates it with the incoming port
3. The entry is stored in the MAC address table
4. The switch uses this table to forward future frames efficiently

---

## Known Unicast Frame
A **Known Unicast** frame occurs when:
- The destination MAC address **exists** in the MAC address table

### Switch Behavior
- The frame is forwarded **only** to the specific port associated with the destination MAC address
- No flooding occurs

---

## Unknown Unicast Frame
An **Unknown Unicast** frame occurs when:
- The destination MAC address **does NOT exist** in the MAC address table

### Switch Behavior
- The frame is **flooded** out all ports **except the source port**
- Once the destination responds, the switch learns the MAC address

---

## Why This Matters
- Improves LAN efficiency
- Reduces unnecessary traffic
- Forms the foundation of switching, VLANs, and network security concepts

---

## Key Takeaways
- Switches forward frames using **MAC addresses**
- The MAC address table is built dynamically
- **Unknown Unicast = Flooding**
- **Known Unicast = Unicast forwarding**
- Ethernet switching is a **Layer 2 process**

---

## CCNA Exam Relevance
This topic is directly tested in **CCNA (200-301)** under:
- Network Fundamentals
- Switching Concepts
- Ethernet LAN switching

---

## Learning Status
✔ Studied  
✔ Documented  
✔ Practiced in Cisco Packet Tracer  

---

## Next Topics
- Broadcast and Multicast frames
- VLAN basics
- ARP and MAC-to-IP mapping
- Switch forwarding vs filtering behavior
