# Lab 09 - RIP Routing

## Objective

To configure RIP Version 2 between two routers and automatically exchange routing information to enable communication between different networks.

---

## Devices Used

- 2 Cisco 1941 Routers
- 2 Cisco 2960 Switches
- 2 PCs

---

## Network Topology

- R1
- R2
- SW1
- SW2
- PC1
- PC2

Two LANs were connected through two routers. RIP Version 2 was configured to automatically exchange routing information between the routers.

---

## IP Addressing

### LAN 1

Network: 192.168.1.0/24

Gateway: 192.168.1.1

### LAN 2

Network: 192.168.2.0/24

Gateway: 192.168.2.1

### Router-to-Router Link

Network: 10.0.0.0/30

R1: 10.0.0.1

R2: 10.0.0.2

---

## RIP Configuration

### R1

```text
router rip
version 2
no auto-summary

network 192.168.1.0
network 10.0.0.0
```

### R2

```text
router rip
version 2
no auto-summary

network 192.168.2.0
network 10.0.0.0
```

---

## Verification

The following commands were used to verify the configuration:

```text
show ip protocols

show ip route

ping
```

The routing table successfully displayed routes learned through RIP, and communication between the two LANs was verified using the ping command.

---

## Learning Outcome

After completing this lab, I learned:

- RIP Version 2 configuration
- Dynamic route exchange
- Hop Count metric
- RIP route verification
- End-to-end communication using dynamic routing

---

## Files Included

- README.md
- lab09-rip-routing.pkt
- lab09-topology.png
- lab09-routing-table.png
- lab09-rip-protocol.png
- lab09-ping-success.png

---

## Troubleshooting

- Verified interface status using `show ip interface brief`
- Verified RIP configuration using `show ip protocols`
- Verified routing table using `show ip route`
- Verified connectivity using the `ping` command

---

## Author

**SRINAVEEN S**

BE Electronics and Communication Engineering

Building My Network Engineering Portfolio
