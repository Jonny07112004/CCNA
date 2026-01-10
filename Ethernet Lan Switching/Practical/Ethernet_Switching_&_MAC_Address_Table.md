


# Practical: Ethernet Switching & MAC Address Table

**Tool:** Cisco Packet Tracer
**Level:** CCNA / Fresher

---

## Objective

* Observe how a switch learns MAC addresses
* Understand **Unknown Unicast** vs **Known Unicast**
* View and verify the **MAC address table**
* Correlate packet flow with switch behavior

---

## Step 1: Create the Topology

### Devices Required

* 1 × Switch (2960)
* 3 × PCs

### Connections

* Use **Copper Straight-Through** cables
* Connect:

  * PC1 → Switch
  * PC2 → Switch
  * PC3 → Switch

No router is required for this experiment.

---

## Step 2: Configure IP Addresses (Same Network)

Configure each PC manually.

### PC1

```
IP Address: 192.168.1.1
Subnet Mask: 255.255.255.0
```

### PC2

```
IP Address: 192.168.1.2
Subnet Mask: 255.255.255.0
```

### PC3

```
IP Address: 192.168.1.3
Subnet Mask: 255.255.255.0
```

(Default gateway is NOT needed.)

---

## Step 3: Clear the Switch MAC Table (Important)

Click the **switch → CLI**:

```text
Switch> enable
Switch# clear mac address-table dynamic
```

Verify it is empty:

```text
Switch# show mac address-table
```

You should see **no dynamic entries**.

---

## Step 4: Enable Simulation Mode

* Switch from **Realtime** to **Simulation**
* Click **Edit Filters**
* Enable only:

  * **ARP**
  * **ICMP**

This avoids clutter.

---

## Step 5: Generate Unknown Unicast Traffic

### Action

* From **PC1**, ping **PC2**

```text
PC1> ping 192.168.1.2
```

### What Happens (Important)

* PC1 sends an **ARP request** (broadcast)
* Switch **learns PC1’s MAC**
* Switch **does not know PC2’s MAC**
* Frame is treated as **Unknown Unicast**
* Switch **floods** the frame to:

  * PC2
  * PC3

This is **Unknown Unicast Flooding**.

---

## Step 6: Observe Packet Flow

In Simulation Mode:

* Click **Next Event**
* Watch packets go to **all ports except the source**

This visually confirms:

> Unknown Unicast → Flooding

---

## Step 7: Check MAC Address Table After Learning

Go back to switch CLI:

```text
Switch# show mac address-table
```

You will now see entries like:

```text
MAC Address        Port
xxxx.xxxx.xxxx     Fa0/1
yyyy.yyyy.yyyy     Fa0/2
```

The switch has **learned MAC addresses dynamically**.

---

## Step 8: Generate Known Unicast Traffic

Now ping again:

```text
PC1> ping 192.168.1.2
```

### What Happens Now

* Switch **already knows** PC2’s MAC
* Frame is forwarded **only to PC2**
* PC3 does **not** receive the frame

This is **Known Unicast Forwarding**.

---

## Step 9: Verify No Flooding

In Simulation Mode:

* Observe packet goes **only to one port**
* No flooding occurs

This confirms:

> Known Unicast → Single-port forwarding

---

## Step 10: (Optional) Observe MAC Aging

Wait a few minutes (default ≈ 300 seconds), then:

```text
Switch# show mac address-table
```

Entries may disappear due to **MAC aging**.

---

## Summary (What You Proved Practically)

| Concept                    | Observed |
| -------------------------- | -------- |
| MAC learning               | Yes      |
| Unknown Unicast flooding   | Yes      |
| Known Unicast forwarding   | Yes      |
| MAC table usage            | Yes      |
| Layer 2 switching behavior | Yes      |

---

## CCNA Exam Mapping

* Ethernet LAN switching
* MAC address table behavior
* Frame forwarding and filtering
* Unknown vs Known Unicast

