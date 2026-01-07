Below is a **clear, CCNA-oriented reference** for **Cisco IOS Router CLI basics**, written for **beginners, interns, and freshers**. This is suitable for inclusion in your **CCNA practice repository** as a quick-reference or lab note.

---

# Cisco IOS Router CLI – Basics

## Accessing the Router CLI

```text
Router>
```

* **User EXEC mode**
* Limited monitoring commands only

---

## Privileged EXEC Mode

```text
Router> enable
Router#
```

* Full access to monitoring and configuration commands

---

## Global Configuration Mode

```text
Router# configure terminal
Router(config)#
```

Used to configure router-wide settings.

---

## Basic Router Identification

### Set Hostname

```text
Router(config)# hostname R1
R1(config)#
```

---

## Password Configuration

### Enable Password (Basic)

```text
R1(config)# enable password cisco
```

### Enable Secret (Recommended)

```text
R1(config)# enable secret class
```

### Console Password

```text
R1(config)# line console 0
R1(config-line)# password cisco
R1(config-line)# login
R1(config-line)# exit
```

### VTY (Telnet/SSH) Password

```text
R1(config)# line vty 0 4
R1(config-line)# password cisco
R1(config-line)# login
R1(config-line)# exit
```

---

## Securing Passwords

### Encrypt Plaintext Passwords

```text
R1(config)# service password-encryption
```

---

## Interface Configuration

### View Interfaces

```text
R1# show ip interface brief
```

### Configure an Interface

```text
R1(config)# interface gigabitEthernet0/0
R1(config-if)# ip address 192.168.1.1 255.255.255.0
R1(config-if)# no shutdown
R1(config-if)# exit
```

---

## Basic Routing

### Static Route

```text
R1(config)# ip route 0.0.0.0 0.0.0.0 192.168.1.254
```

---

## Verification Commands

```text
R1# show running-config
R1# show startup-config
R1# show ip route
R1# show interfaces
R1# ping 8.8.8.8
R1# traceroute 8.8.8.8
```

---

## Saving Configuration

```text
R1# copy running-config startup-config
```

or

```text
R1# write memory
```

---

## Exiting Modes

```text
exit        ← step back one mode
end         ← return to privileged EXEC
disable     ← return to user EXEC
```

---

## Helpful CLI Shortcuts

* `?` → Context-sensitive help
* `Tab` → Auto-complete command
* `Ctrl + Z` → Exit to privileged EXEC
* `Ctrl + C` → Abort command

---

## Common Mistakes (Beginner Tips)

* Forgetting `no shutdown` on interfaces
* Not saving configuration before reboot
* Using `enable password` instead of `enable secret`
* Wrong subnet mask on interfaces

---

## CCNA Exam Relevance

This CLI knowledge is essential for:

* Router and switch configuration
* Troubleshooting connectivity
* Understanding network device behavior
* Performing CCNA 200-301 practical questions


