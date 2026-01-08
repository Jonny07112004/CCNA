




# Cisco IOS CLI Practical: Hostname & Enable Password Configuration

## Lab Objective

* Configure hostnames on a router and switch
* Set and verify enable passwords
* Understand password encryption behavior in Cisco IOS
* Save configuration correctly

---

## Device 1: Router (R1)

### 1. Enter Privileged EXEC Mode

```bash
Router> enable
Router#
```

---

### 2. Enter Global Configuration Mode

```bash
Router# configure terminal
Router(config)#
```

---

### 3. Change Hostname to R1

```bash
Router(config)# hostname R1
R1(config)#
```

---

### 4. Configure an Unencrypted Enable Password (`CCNA`)

```bash
R1(config)# enable password CCNA
```

---

### 5. Exit to User EXEC Mode and Test Password

```bash
R1(config)# end
R1# disable
R1>
```

Re-enter privileged mode:

```bash
R1> enable
Password: CCNA
R1#
```

---

### 6. View Password in Running Configuration

```bash
R1# show running-config
```

You will see:

```text
enable password CCNA
```

(The password is visible in plain text.)

---

### 7. Encrypt All Current and Future Passwords

```bash
R1(config)# service password-encryption
```

---

### 8. Verify Encrypted Password

```bash
R1# show running-config
```

Now you will see:

```text
enable password 7 <encrypted-value>
```

---

### 9. Configure a Secure Encrypted Enable Secret Password (`Cisco`)

```bash
R1(config)# enable secret Cisco
```

---

### 10. Exit and Test Which Password Is Used

```bash
R1(config)# end
R1# disable
R1>
R1> enable
Password: Cisco
R1#
```

**Answer:**
The router uses **enable secret**, not `enable password`.

---

### 11. Verify Encryption Types

```bash
R1# show running-config
```

You will see:

```text
enable password 7 <encrypted>
enable secret 5 <encrypted>
```

#### Encryption Type Explanation

| Type   | Meaning                             |
| ------ | ----------------------------------- |
| Type 7 | Weak reversible encryption          |
| Type 5 | MD5 hash (stronger, non-reversible) |

---

### 12. Save Configuration

```bash
R1# copy running-config startup-config
```

---

## Device 2: Switch (SW1)

### 1. Enter Privileged EXEC Mode

```bash
Switch> enable
Switch#
```

---

### 2. Enter Global Configuration Mode

```bash
Switch# configure terminal
Switch(config)#
```

---

### 3. Change Hostname to SW1

```bash
Switch(config)# hostname SW1
SW1(config)#
```

---

### 4. Configure Enable Password (`CCNA`)

```bash
SW1(config)# enable password CCNA
```

---

### 5. Encrypt Passwords

```bash
SW1(config)# service password-encryption
```

---

### 6. Configure Enable Secret (`Cisco`)

```bash
SW1(config)# enable secret Cisco
```

---

### 7. Verify Running Configuration

```bash
SW1# show running-config
```

---

### 8. Save Configuration

```bash
SW1# copy running-config startup-config
```

---

## Key CCNA Takeaways

* `enable secret` always overrides `enable password`
* `service password-encryption` uses **Type 7** encryption
* `enable secret` uses **Type 5** encryption
* Always save configuration after changes




