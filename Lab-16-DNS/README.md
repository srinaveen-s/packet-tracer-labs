# Lab 16 - Domain Name System (DNS)

## 🎯 Objective

The objective of this lab is to configure a DNS server and a web server, then verify that a client PC can access the website using a domain name instead of an IP address.

---

## 🛠️ Devices Used

- 1 Cisco 1941 Router
- 1 Cisco 2960 Switch
- 1 PC
- 1 DNS Server
- 1 Web Server

---

## 🌐 Network Topology

```
             R1
              |
             SW1
      ________|________
     |        |        |
    PC1   DNS Server  Web Server
```

---

## 📋 IP Addressing

| Device | Interface | IP Address | Subnet Mask |
|---------|-----------|------------|-------------|
| R1 | G0/0 | 192.168.1.1 | 255.255.255.0 |
| PC1 | NIC | 192.168.1.10 | 255.255.255.0 |
| DNS Server | Fa0 | 192.168.1.2 | 255.255.255.0 |
| Web Server | Fa0 | 192.168.1.100 | 255.255.255.0 |

**Default Gateway:** `192.168.1.1`

**DNS Server:** `192.168.1.2`

---

## ⚙️ Configuration Summary

### Configure Router

```bash
enable
configure terminal

interface GigabitEthernet0/0
ip address 192.168.1.1 255.255.255.0
no shutdown

end
write
```

---

### Configure DNS Server

Go to:

```
Services → DNS
```

Enable DNS service.

```
DNS : ON
```

Add the following DNS record:

| Name | Address |
|------|----------|
| www.company.local | 192.168.1.100 |

---

### Configure Web Server

Go to:

```
Services → HTTP
```

Enable HTTP service.

```
HTTP : ON
```

Edit **index.html** and create a custom webpage.

Example:

```html
<h1>Welcome to Company Website</h1>
<h2>DNS Lab Successful</h2>
<p>This website is accessed using the domain name www.company.local.</p>
```

---

### Configure PC

| Setting | Value |
|----------|-------|
| IP Address | 192.168.1.10 |
| Subnet Mask | 255.255.255.0 |
| Default Gateway | 192.168.1.1 |
| DNS Server | 192.168.1.2 |

---

## ✅ Verification

Verify DNS resolution:

```text
ping www.company.local
```

Expected Result:

```
Reply from 192.168.1.100
```

Verify website access:

Open Web Browser and enter:

```text
http://www.company.local
```

The custom webpage should load successfully.

---

## 📸 Screenshots

- Network Topology
- DNS Configuration
- Web Server Configuration
- Ping Test
- Browser Test

---

## 📚 Key Learning Outcomes

- Understood the purpose of DNS.
- Configured a DNS server in Cisco Packet Tracer.
- Created an A Record for domain name resolution.
- Configured an HTTP web server.
- Configured a client PC to use a DNS server.
- Verified successful DNS name resolution using Ping.
- Accessed a website using a domain name instead of an IP address.

---

## ✅ Result

Successfully configured a DNS server and a web server in Cisco Packet Tracer. The client PC successfully resolved the domain name **www.company.local** to the web server's IP address and accessed the website through the web browser.

---

# 👨‍💻 Author

**Srinaveen S**

Passionate Electronics and Communication Engineering student with a strong interest in Computer Networks, Cisco Networking, and Network Security. This lab was created as part of my hands-on networking practice using Cisco Packet Tracer to strengthen practical networking skills.
