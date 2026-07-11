# Lab 06 - Spanning Tree Protocol (STP)

## Objective

To understand how Spanning Tree Protocol (STP) prevents Layer 2 network loops by blocking redundant paths while maintaining network connectivity.

---

## Devices Used

- 3 Cisco 2960 Switches
- 2 PCs

---

## Network Topology

- SW1
- SW2
- SW3
- PC1
- PC2

The three switches were connected in a triangle topology to create a redundant path.

---

## Configuration

No manual STP configuration was required because STP is enabled by default on Cisco switches.

The following command was used to verify STP:

```bash
show spanning-tree
```

---

## Verification

The `show spanning-tree` command confirmed:

- Root Bridge election
- Root Port selection
- Designated Ports
- Alternate Blocking Port

One redundant port entered the **Blocking** state, preventing a switching loop.

Communication between PC1 and PC2 was verified successfully using the **ping** command.

---

## Learning Outcome

After completing this lab, I learned:

- How STP prevents Layer 2 loops
- Root Bridge election process
- Root Port and Designated Port roles
- Blocking Port functionality
- Basic STP verification using Cisco CLI

---

## Files Included

- README.md
- lab06-spanning-tree-protocol.pkt
- lab06-topology.png
- lab06-stp-output.png
- lab06-blocking-port.png
- lab06-ping-success.png

---

## Commands Used

```text
enable

show spanning-tree
```

---

## Author

**SRINAVEEN S**

BE Electronics and Communication Engineering

Building My Network Engineering Portfolio
