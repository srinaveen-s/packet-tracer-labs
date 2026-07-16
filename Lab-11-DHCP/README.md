# Lab 11 - DHCP Configuration

## Objective

Configure a Cisco router as a DHCP server and automatically assign IP addresses to client devices.

---

## Devices Used

- 1 Cisco 1941 Router
- 1 Cisco 2960 Switch
- 1 PC

---

## DHCP Configuration

```text
ip dhcp excluded-address 192.168.1.1

ip dhcp pool OFFICE
network 192.168.1.0 255.255.255.0
default-router 192.168.1.1
dns-server 8.8.8.8
```

---

## Verification Commands

```text
show ip dhcp binding
show running-config
ping
```

---

## Results

- DHCP server configured successfully.
- IP address assigned automatically to the client.
- Gateway and DNS configured successfully.
- Network connectivity verified using the ping command.

---

## Files Included

- README.md
- lab11-dhcp.pkt
- lab11-topology.png
- lab11-dhcp-config.png
- lab11-ip-assignment.png
- lab11-ping-success.png

---

## Author

**SRINAVEEN S**

BE Electronics and Communication Engineering

Aspiring Network & Telecom Engineer

Building practical networking skills through hands-on labs and real-world troubleshooting.
