# Lab 08 - Static Routing

## Objective

To configure Static Routing between two routers and enable communication between two different LANs.

---

## Devices Used

- 2 Cisco Routers
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

Two LANs were connected through two routers. Static routes were configured to allow communication between the networks.

---

## IP Addressing

### LAN 1

Network: 192.168.1.0/24

Gateway: 192.168.1.1

---

### LAN 2

Network: 192.168.2.0/24

Gateway: 192.168.2.1

---

### Router-to-Router Link

Network: 10.0.0.0/30

R1: 10.0.0.1

R2: 10.0.0.2

---

## Configuration

Static Route on R1

```text
ip route 192.168.2.0 255.255.255.0 10.0.0.2
```

Static Route on R2

```text
ip route 192.168.1.0 255.255.255.0 10.0.0.1
```

---

## Verification

The routing table was verified using:

```text
show ip route
```

End-to-end communication was successfully verified using the **ping** command.

---

## Learning Outcome

After completing this lab, I learned:

- Router interface configuration
- Static Route configuration
- Routing table verification
- Next-hop IP concept
- End-to-end network communication

---

## Files Included

- README.md
- lab08-static-routing.pkt
- lab08-topology.png
- lab08-routing-table.png
- lab08-ping-success.png

---

## Commands Used

```text
show ip route

ping
```

---

## Troubleshooting

- Verified interface status using `show ip interface brief`.
- Verified routing table using `show ip route`.
- Checked default gateway configuration on both PCs.
- Verified end-to-end communication using the `ping` command.

---

## Author

**SRINAVEEN S**

BE Electronics and Communication Engineering

Building My Network Engineering Portfolio
