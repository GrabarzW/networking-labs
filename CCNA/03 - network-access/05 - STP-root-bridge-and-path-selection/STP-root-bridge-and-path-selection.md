# STP Root Bridge and Path Selection

## Objective

Analyze and manipulate Spanning Tree Protocol (STP) behavior by changing root bridge priority, interface cost, and port priority for different VLANs.

The lab focuses on per-VLAN STP topology, root bridge selection, root port selection, and STP path-selection criteria.

## Tasks

1. Analyze the initial STP topology using the Cisco IOS CLI.
2. Identify the current root bridge and STP role/state of each interface.
3. Configure:

   * SW1 as the primary root for VLAN 1.
   * SW1 as the secondary root for VLAN 2.
   * SW2 as the primary root for VLAN 2.
   * SW2 as the secondary root for VLAN 1.
4. Analyze the resulting STP topology.
5. Increase the VLAN 1 STP cost of SW4 F0/2 to 100 and determine whether SW4 selects a different root port.
6. Increase the VLAN 1 port priority of SW1 F0/1 to 240 and determine whether SW3 selects a different root port.
7. Configure PortFast and BPDU Guard on SW3/SW4 F0/3.

## Concepts

* Spanning Tree Protocol (STP)
* Root bridge election
* Primary and secondary root bridge
* Per-VLAN STP
* Root port
* Designated port
* Blocking port
* STP path cost
* STP port priority
* STP path selection
* PortFast
* BPDU Guard
* Layer 2 loop prevention

## Initial Topology

The initial root bridge is:

**SW2**

### Initial STP Port Roles

| Switch | VLAN   | F0/1 | F0/2 | F0/3 |
| ------ | ------ | ---- | ---- | ---- |
| SW1    | VLAN 1 | BLK  | DES  | ROOT |
| SW1    | VLAN 2 | BLK  | DES  | ROOT |
| SW2    | VLAN 1 | DES  | DES  | DES  |
| SW2    | VLAN 2 | DES  | DES  | DES  |
| SW3    | VLAN 1 | DES  | ROOT | DES  |
| SW3    | VLAN 2 | DES  | ROOT | —    |
| SW4    | VLAN 1 | ROOT | BLK  | —    |
| SW4    | VLAN 2 | ROOT | BLK  | DES  |

## STP Root Bridge Configuration

The STP topology was modified so that:

* SW1 becomes the primary root for VLAN 1.
* SW2 becomes the primary root for VLAN 2.
* SW1 becomes the secondary root for VLAN 2.
* SW2 becomes the secondary root for VLAN 1.

This creates different preferred STP topologies for VLAN 1 and VLAN 2.

## STP Cost Experiment

The VLAN 1 STP cost of SW4 F0/2 was increased to **100**.

### Result

**SW4 selects a different root port.**

The increased interface cost makes the path through F0/2 less attractive compared with the alternative path.

This demonstrates that STP uses cumulative path cost when selecting the best path toward the root bridge.

## STP Port Priority Experiment

The VLAN 1 port priority of SW1 F0/1 was increased to **240**.

### Result

**SW3 does not select a different root port.**

Changing port priority alone does not override better STP path-selection criteria. Root path cost and the relevant bridge/port identifiers are evaluated before the local port ID becomes the deciding factor.

This demonstrates that port priority is only one of several STP tie-breaking criteria.

## PortFast and BPDU Guard

PortFast and BPDU Guard were configured on:

* SW3 F0/3
* SW4 F0/3

These features are intended for edge/access ports connected to end devices.

**PortFast** allows an access port to transition to the forwarding state without waiting through the normal STP transition process.

**BPDU Guard** protects the topology by placing the port into an error-disabled state if a BPDU is received on a PortFast-enabled interface.

## Verification

Useful Cisco IOS commands:

```text
show spanning-tree
show spanning-tree vlan 1
show spanning-tree vlan 2
show spanning-tree interface f0/1
show spanning-tree interface f0/2
show spanning-tree interface f0/3
spanning-tree vlan 1 cost
spanning-tree vlan 1 port-priority
spanning-tree portfast
spanning-tree bpduguard enable

These commands can be used to verify:
```

* Root bridge
* Root port
* Designated ports
* Blocking ports
* STP cost
* Port priority
* PortFast
* BPDU Guard

## Key Findings

* STP can build different Layer 2 topologies for different VLANs.
* Root bridge selection can be intentionally influenced using bridge priority.
* Primary and secondary root configurations provide predictable STP topology and redundancy.
* STP path cost directly influences root port selection.
* Increasing an interface cost can cause a switch to select an alternative path.
* Port priority is a later STP tie-breaking criterion and does not necessarily change the selected root port.
* PortFast improves edge-port convergence for end devices.
* BPDU Guard protects edge ports against unexpected Layer 2 topology changes.

## Skills Demonstrated

* Cisco IOS CLI
* STP configuration and analysis
* Root bridge manipulation
* Per-VLAN STP
* Root port and designated port analysis
* STP cost manipulation
* STP port priority
* STP path-selection analysis
* PortFast configuration
* BPDU Guard configuration
* Layer 2 loop prevention
* Network troubleshooting and verification
