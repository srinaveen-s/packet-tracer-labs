# Lab 13 - Access Control List (ACL)

## 🎯 Objective

The objective of this lab is to configure a Standard Access Control List (ACL) to control network traffic. In this lab, one host is denied access to the external network while the remaining hosts are allowed to communicate successfully.

---

## 🛠️ Devices Used

- 2 Cisco 1941 Routers
- 1 Cisco 2960 Switch
- 3 PCs

---

## 🌐 Network Topology

```
        R2
         |
         |
        R1
         |
       SW1
    /    |    \
  PC1   PC2   PC3
```

---

## 📋 IP Addressing

| Device | Interface | IP Address | Subnet Mask |
|---------|-----------|------------|-------------|
| R1 | G0/0 | 192.168.1.1 | 255.255.255.0 |
| R1 | G0/1 | 209.165.200.226 | 255.255.255.252 |
| R2 | G0/0 | 209.165.200.225 | 255.255.255.252 |
| PC1 | NIC | 192.168.1.10 | 255.255.255.0 |
| PC2 | NIC | 192.168.1.20 | 255.255.255.0 |
| PC3 | NIC | 192.168.1.30 | 255.255.255.0 |

**Default Gateway (All PCs):** `192.168.1.1`

---

## ⚙️ Configuration Summary

### Configure Router Interfaces

Assigned IP addresses to the router interfaces and enabled them using the `no shutdown` command.

### Configure Static Route

Configured a static route on R2 to reach the internal network.

```bash
ip route 192.168.1.0 255.255.255.0 209.165.200.226
```

### Configure Standard ACL

Created a Standard ACL to deny traffic from PC1 while permitting all other traffic.

```bash
access-list 10 deny host 192.168.1.10
access-list 10 permit any
```

Applied the ACL to the outbound direction of the router interface.

```bash
interface GigabitEthernet0/1
ip access-group 10 out
```

---

## ✅ Verification

The following command was used to verify the ACL configuration:

```bash
show access-lists
```

Connectivity was verified using:

```bash
ping 209.165.200.225
```

### Verification Results

- ❌ PC1 - Access Denied
- ✅ PC2 - Access Allowed
- ✅ PC3 - Access Allowed

---

## 📸 Screenshots

- Network Topology
- ACL Configuration
- PC1 Blocked Verification
- PC2 Successful Ping
- PC3 Successful Ping

---

## 📚 Key Learning Outcomes

- Configured a Standard Access Control List (ACL).
- Applied ACLs to router interfaces.
- Controlled network traffic using permit and deny rules.
- Verified ACL functionality using Cisco IOS commands.
- Understood the importance of ACL placement and rule order.

---

## ✅ Result

Successfully configured and verified a Standard Access Control List (ACL). The configured ACL blocked traffic from PC1 while allowing communication from PC2 and PC3, demonstrating effective traffic filtering using Cisco IOS.
## 👨‍💻 Author

**Srinaveen S**

Passionate Electronics and Communication Engineering student with a strong interest in Computer Networks, Cisco Networking, and Network Security. This lab was created as part of my hands-on networking practice using Cisco Packet Tracer to strengthen practical networking skills.
