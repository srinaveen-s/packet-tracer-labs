# Lab 15 - Secure Shell (SSH)

## 🎯 Objective

The objective of this lab is to configure Secure Shell (SSH) on a Cisco router and securely access the router from a PC using an encrypted remote connection.

---

## 🛠️ Devices Used

- 1 Cisco 1941 Router
- 1 Cisco 2960 Switch
- 1 PC

---

## 🌐 Network Topology

```
      R1
       |
      SW1
       |
      PC1
```

---

## 📋 IP Addressing

| Device | Interface | IP Address | Subnet Mask |
|---------|-----------|------------|-------------|
| R1 | G0/0 | 192.168.1.1 | 255.255.255.0 |
| PC1 | NIC | 192.168.1.10 | 255.255.255.0 |

**Default Gateway:** `192.168.1.1`

---

## ⚙️ Configuration Summary

### Configure Router Interface

```bash
interface GigabitEthernet0/0
ip address 192.168.1.1 255.255.255.0
no shutdown
```

---

### Configure SSH

Configure the router hostname, domain name, local user, generate RSA keys, and enable SSH Version 2.

```bash
hostname R1

ip domain-name lab.local

username admin secret Cisco123

crypto key generate rsa
```

When prompted for the key size, enter:

```text
1024
```

Complete the SSH configuration:

```bash
ip ssh version 2

line vty 0 4
login local
transport input ssh
```

Save the configuration:

```bash
end

write
```

---

## ✅ Verification

Verify SSH status:

```bash
show ip ssh
```

Verify the running configuration:

```bash
show running-config
```

Connect to the router from the PC:

```bash
ssh -l admin 192.168.1.1
```

---

## 📸 Screenshots

- Network Topology
- SSH Configuration
- SSH Status (`show ip ssh`)
- Successful SSH Login (`R1>`)

---

## 📚 Key Learning Outcomes

- Configured SSH on a Cisco router.
- Generated RSA keys for encrypted communication.
- Created a local username and password.
- Enabled SSH Version 2.
- Configured VTY lines for secure remote access.
- Verified successful SSH login from a client PC.

---

## ✅ Result

Successfully configured and verified Secure Shell (SSH) on a Cisco router. A secure remote connection was established from the PC using SSH authentication, demonstrating encrypted remote device management.

---

# 👨‍💻 Author

**Srinaveen S**

Passionate Electronics and Communication Engineering student with a strong interest in Computer Networks, Cisco Networking, and Network Security. This lab was created as part of my hands-on networking practice using Cisco Packet Tracer to strengthen practical networking skills.
