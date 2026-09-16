\# Rapid Spanning Tree Protocol



\## Objective



Analyze Rapid Spanning Tree Protocol (RSTP) behavior by identifying the root bridge, port roles, port states, and link types in a topology containing point-to-point and shared-media connections.



The lab also focuses on manually configuring appropriate RSTP link types and understanding the `Edge`, `Point-to-Point`, and `Shared` classifications.



\## Tasks



1\. Identify the root bridge using the CLI.

2\. Examine the port roles and states on the root bridge.

3\. Identify what differs from the expected STP behavior of a root bridge and determine the cause.

4\. Determine the port roles and states of the remaining switches without initially using the CLI.

5\. Use the CLI to verify the predicted topology.

6\. Manually configure the appropriate RSTP link type on each interface.

7\. Determine the appropriate link type for SW1 F0/24.



\## Concepts



\* Rapid Spanning Tree Protocol (RSTP)

\* Root bridge

\* Root port

\* Designated port

\* Alternate port

\* Backup port

\* Edge port

\* Point-to-point link

\* Shared link

\* STP/RSTP topology

\* Layer 2 loop prevention

\* RSTP link types



\## Root Bridge



The root bridge is:



\*\*SW1\*\*



\### Root Bridge Port Roles



| Interface | Role       | Link Type      |

| --------- | ---------- | -------------- |

| F0/24     | Designated | Edge           |

| F0/3      | Backup     | Shared         |

| F0/1      | Designated | Point-to-Point |

| F0/2      | Designated | Point-to-Point |



Normally, interfaces on the root bridge operate as designated ports.



The exception in this topology is SW1 F0/3, which operates as a backup port.



\### Why is F0/3 a Backup Port?



SW1 is connected to a hub using multiple physical connections.



A hub creates a shared Layer 2 segment. Because multiple switch interfaces connect to the same shared segment, RSTP can identify one interface as the designated path and another as a backup path.



This is different from a typical switch-to-switch point-to-point connection.



\## Predicted RSTP Topology



The remaining switch interfaces were analyzed based on RSTP path selection and the topology before verifying the results using the CLI.



\### SW2



| Interface | Role       | Link Type      |

| --------- | ---------- | -------------- |

| F0/1      | Root       | Point-to-Point |

| F0/2      | Designated | Point-to-Point |

| F0/23     | Designated | Edge           |

| F0/24     | Designated | Edge           |

| G0/1      | Alternate  | Point-to-Point |



\### SW3



| Interface | Role       | Link Type      |

| --------- | ---------- | -------------- |

| F0/1      | Designated | Point-to-Point |

| F0/2      | Root       | Shared         |

| F0/24     | Designated | Edge           |

| G0/1      | Designated | Point-to-Point |



\### SW4



| Interface | Role       | Link Type      |

| --------- | ---------- | -------------- |

| F0/1      | Root       | Point-to-Point |

| F0/2      | Alternate  | Point-to-Point |

| F0/24     | Designated | Edge           |



\## SW1 F0/24 RSTP Link Type



The appropriate link type for \*\*SW1 F0/24\*\* is:



Edge



The interface is connected to an end device, so it should operate as an edge port.



\## Verification



\# Useful Cisco IOS commands:



* show spanning-tree
* spanning-tree portfast
* spanning-tree link-type point-to-point
* spanning-tree link-type shared





These commands can be used to verify:



* Root bridge
* Root port
* Designated ports
* Alternate ports
* Backup ports
* RSTP states
* Link types
* Edge-port configuration



\## Key Findings



* The root bridge does not necessarily have every interface operating as a designated port.
* RSTP can use backup ports when multiple interfaces connect to the same shared-media segment.
* A hub creates a shared-media segment that behaves differently from a full-duplex switch-to-switch link.
* RSTP distinguishes between point-to-point, shared, and edge links.
* Alternate ports provide an alternative path toward the root bridge.
* Backup ports provide redundancy for a designated port on the same shared segment.
* Edge ports are intended for connections to end devices.
* Correct RSTP link-type configuration helps the protocol properly interpret the network topology.



\## Skills Demonstrated



* Cisco IOS CLI
* RSTP analysis
* Root bridge identification
* RSTP port-role identification
* Root, designated, alternate, and backup ports
* RSTP link-type configuration
* Point-to-point link analysis
* Shared-media analysis
* Edge-port configuration
* Layer 2 loop prevention
* STP/RSTP troubleshooting and verification



