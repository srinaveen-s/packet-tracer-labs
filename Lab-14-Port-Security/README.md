# Lab 14 - Port Security

## 🎯 Objective

The objective of this lab is to configure Port Security on a Cisco switch to allow only one authorized device to access the network. If an unauthorized device connects to the secured port, the configured violation action is triggered.

---

## 🛠️ Devices Used

- 1 Cisco 1941 Router
- 1 Cisco 2960 Switch
- 2 PCs

---

## 🌐 Network Topology

```
        R1
         |
        SW1
       /   \
    PC1    PC2
```

---

## 📋 IP Addressing

| Device | Interface | IP Address | Subnet Mask |
|---------|-----------|------------|-------------|
| R1 | G0/0 | 192.168.1.1 | 255.255.255.0 |
| PC1 | NIC | 192.168.1.10 | 255.255.255.0 |
| PC2 | NIC | 192.168.1.20 | 255.255.255.0 |

**Default Gateway (PC1 & PC2):** `192.168.1.1`

---

## ⚙️ Configuration Summary

### Configure Switch Port

Configured the switch port as an access port and enabled Port Security.

```bash
interface FastEthernet0/1

switchport mode access

switchport port-security

switchport port-security maximum 1

switchport port-security mac-address sticky

switchport port-security violation shutdown
```

---

## ✅ Verification

The following commands were used to verify the Port Security configuration:

```bash
show port-security

show port-security interface FastEthernet0/1

show running-config
```

### Verification Results

- ✅ PC1 successfully connected to the switch.
- ✅ Sticky MAC address was learned automatically.
- ❌ When PC2 was connected to the secured port, the port entered the Err-Disabled (Shutdown) state.
- ✅ Port Security violation was successfully detected.

---

## 📸 Screenshots

- Network Topology
- Port Security Configuration
- Sticky MAC Address
- Port Security Status
- Violation Detection (Err-Disabled)
- Verification Commands

---

## 📚 Key Learning Outcomes

- Configured Port Security on a Cisco switch.
- Secured a switch port using Sticky MAC.
- Limited the number of allowed MAC addresses.
- Configured the Shutdown violation mode.
- Verified Port Security using Cisco IOS commands.
- Understood how Port Security protects Layer 2 networks from unauthorized access.

---

## ✅ Result

Successfully configured and verified Port Security on a Cisco switch. The switch allowed only the authorized device to connect, while an unauthorized device triggered a security violation and caused the port to enter the Err-Disabled state.

---

# 👨‍💻 Author

**Srinaveen S**

Passionate Electronics and Communication Engineering student with a strong interest in Computer Networks, Cisco Networking, and Network Security. This lab was created as part of my hands-on networking practice using Cisco Packet Tracer to strengthen practical networking skills.
