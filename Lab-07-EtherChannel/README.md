# Lab 07 - EtherChannel Configuration

## Objective

To configure EtherChannel using LACP (Link Aggregation Control Protocol) and combine multiple physical links into a single logical link between two switches.

---

## Devices Used

- 2 Cisco 2960 Switches
- 2 PCs

---

## Network Topology

- SW1
- SW2
- PC1
- PC2

Two physical links were configured between the switches and grouped into a single Port-Channel using LACP.

---

## Configuration

EtherChannel was configured using the following commands:

```text
interface range fastEthernet 0/23 - 24
channel-group 1 mode active

interface port-channel 1
switchport mode trunk
```

---

## Verification

The following command was used to verify the EtherChannel configuration:

```text
show etherchannel summary
```

The output confirmed that both FastEthernet interfaces were successfully added to Port-Channel 1.

Communication between PC1 and PC2 was verified successfully using the **ping** command.

---

## Learning Outcome

After completing this lab, I learned:

- EtherChannel configuration using LACP
- Port-Channel interface creation
- Link aggregation concepts
- EtherChannel verification using Cisco CLI
- Basic load balancing and redundancy concepts

---

## Files Included

- README.md
- lab07-etherchannel-configuration.pkt
- lab07-topology.png
- lab07-etherchannel-summary.png
- lab07-ping-success.png

---

## Commands Used

```text
enable

configure terminal

interface range fastEthernet 0/23 - 24

channel-group 1 mode active

interface port-channel 1

switchport mode trunk

show etherchannel summary
```

---

## Troubleshooting

- Verified EtherChannel status using `show etherchannel summary`.
- Confirmed both interfaces were added to Port-Channel 1.
- Verified connectivity using the `ping` command.

---

## Author

**SRINAVEEN S**

BE Electronics and Communication Engineering

Building My Network Engineering Portfolio
