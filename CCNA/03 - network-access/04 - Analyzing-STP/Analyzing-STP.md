\# Spanning Tree Protocol



\## Objective



Analyze a redundant Layer 2 network topology and identify the Spanning

Tree Protocol (STP) root bridge and the role of each switch port.



Use Cisco IOS CLI to verify the STP topology and port roles.



\## Tasks



* Identify the STP root bridge.
* Identify the role of each switch port.
* Classify ports as Root, Designated, or Non-Designated.
* Analyze the resulting Layer 2 topology.
* Verify the observations using Cisco IOS show commands.



\## Topology



The network contains four switches with redundant Layer 2 paths.



To make the STP port states easier to analyze, Packet Tracer link lights

were disabled for this lab.



\## STP Topology



\### Root Bridge



The root bridge is:



\*\*SW3\*\*



\### Port Roles



| Switch | Interface | Role           |

| SW1    | F0/1      | Non-Designated |

| SW1    | F0/2      | Non-Designated |

| SW1    | F0/3      | Non-Designated |

| SW1    | F0/4      | Root           |

| SW2    | F0/1      | Designated     |

| SW2    | F0/2      | Designated     |

| SW2    | F0/3      | Non-Designated |

| SW2    | G0/1      | Root           |

| SW3    | F0/1      | Designated     |

| SW3    | F0/2      | Designated     |

| SW3    | F0/3      | Designated     |

| SW3    | G0/1      | Designated     |

| SW4    | G0/1      | Designated     |

| SW4    | G0/2      | Root           |



\## Concepts



* Spanning Tree Protocol (STP)
* Root bridge
* Root port
* Designated port
* Non-designated port
* Layer 2 loops
* Redundant paths
* STP topology
* Layer 2 network convergence



\## Verification



The STP topology was verified using Cisco IOS CLI commands.



The root bridge and individual port roles were compared with the expected

topology observed in Packet Tracer.



\## Key Findings



* STP prevents Layer 2 switching loops in redundant network topologies.
* The root bridge provides the reference point for STP path selection.
* Each non-root switch uses a root port to reach the root bridge.
* Designated ports forward traffic for their respective network segments.
* Non-designated ports are placed into a blocking state to prevent Layer 2 loops.
* Redundant physical links can therefore exist without creating an active switching loop.



\## Skills Demonstrated



* Cisco IOS CLI
* STP analysis
* Root bridge identification
* STP port role identification
* Layer 2 topology analysis
* Redundancy and loop prevention
* Network verification

