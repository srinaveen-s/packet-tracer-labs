# Lab 05 - Inter-VLAN Routing (Router-on-a-Stick)

## Objective

Configure Inter-VLAN Routing using Router-on-a-Stick so that devices in different VLANs can communicate with each other.

---

## Devices Used

- Cisco 1941 Router
- Cisco 2960 Switch
- 4 PCs

---

## VLAN Configuration

VLAN 10 - Admin & HR

VLAN 20 - Finance

VLAN 30 - IT

---

## Router Configuration

Configured Router Subinterfaces:

- GigabitEthernet0/0.10
- GigabitEthernet0/0.20
- GigabitEthernet0/0.30

IEEE 802.1Q encapsulation was used for each VLAN.

---

## Verification

Successful communication was verified between different VLANs using the ping command.

The first ping packet timed out because of ARP resolution, and subsequent packets were successful.

---

## Learning Outcome

After completing this lab, I learned:

- VLAN Configuration
- Trunk Port Configuration
- Router-on-a-Stick
- IEEE 802.1Q Encapsulation
- Inter-VLAN Routing
- Default Gateway Configuration

---

## Files Included

- README.md
- lab05-inter-vlan-routing.pkt
- lab05-topology.png
- lab05-router-subinterfaces.png
- lab05-ping-success.png

---

Author: SRINAVEEN S
