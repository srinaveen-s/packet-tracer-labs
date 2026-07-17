# Lab 12 - Network Address Translation (NAT)

## 🎯 Objective

The objective of this lab is to configure Network Address Translation (NAT) using PAT (NAT Overload) on a Cisco router. This allows multiple devices in a private network to communicate with an external network using a single public IP address.

---

## 🛠️ Devices Used

- 2 Cisco 1941 Routers
- 1 Cisco 2960 Switch
- 3 PCs

---

## 🌐 Network Topology

```
        R2 (ISP)
           |
           |
        R1 (NAT)
           |
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

### Configure IP Addresses
- Assigned IP addresses to routers and PCs.
- Enabled router interfaces using `no shutdown`.

### Configure Static Route

Configured a static route on R2 to reach the internal network.

```bash
ip route 192.168.1.0 255.255.255.0 209.165.200.226
```

### Configure NAT

Configured the inside and outside NAT interfaces.

```bash
interface GigabitEthernet0/0
ip nat inside

interface GigabitEthernet0/1
ip nat outside
```

Created an ACL for the private network.

```bash
access-list 1 permit 192.168.1.0 0.0.0.255
```

Enabled PAT (NAT Overload).

```bash
ip nat inside source list 1 interface GigabitEthernet0/1 overload
```

---

## ✅ Verification

The following commands were used to verify NAT configuration:

```bash
show ip nat translations
show ip nat statistics
```

Connectivity was also verified using:

```bash
ping 209.165.200.225
```

---

## 📸 Screenshots

- Network Topology
- Router Ping Verification
- PC Ping Verification
- NAT Translations
- NAT Statistics

---

## 📚 Key Learning Outcomes

- Configured router interfaces.
- Configured static routing.
- Configured NAT Inside and Outside interfaces.
- Created an Access Control List (ACL) for NAT.
- Implemented PAT (NAT Overload).
- Verified NAT using Cisco IOS commands.

---

## ✅ Result

Successfully configured and verified Network Address Translation (PAT Overload). Internal devices were able to communicate with the external network using a single public IP address.
## 👨‍💻 Author

**Srinaveen S**

Electronics and Communication Engineering student passionate about networking and network engineering. Building practical Cisco Packet Tracer labs to enhance hands-on networking skills.
