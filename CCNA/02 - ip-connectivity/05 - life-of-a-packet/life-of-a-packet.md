\# Life of a Packet



\## Objective



Analyze how Ethernet frames are forwarded through a routed network and

identify the source and destination MAC addresses at each network segment.



Use Cisco IOS commands and Packet Tracer Simulation Mode to follow the

traffic generated between different end devices.



\## Tasks



* Analyze PC1 pinging PC4.
* Identify the source and destination MAC addresses at each network segment.
* Analyze PC1 pinging PC3.
* Identify the source and destination MAC addresses on the local segment.
* Analyze PC4 pinging PC1.
* Verify the results using Cisco IOS CLI and Packet Tracer Simulation Mode.



\## MAC Address Reference



| Device | Interface | MAC Address      |

|  PC1   |    NIC    | 00D0.BA11.1111   |

|  R1    |    G0/0   | 0000.01AA.AAAA   |

|  R1    |    G0/1   | 0000.01BB.BBBB   |

|  R2    |    G0/0   | 0000.01CC.CCCC   |

|  R2    |    G0/1   | 0000.01DD.DDDD   |

|  R3    |    G0/0   | 0000.01EE.EEEE   |

|  R3    |    G0/1   | 0000.01FF.FFFF   |

|  PC3   |    NIC    | 0010.1133.3333   |

|  PC4   |    NIC    | 000C.8544.4444   |



\## PC1 → PC4



| Segment   | Source MAC       | Destination MAC  |

| PC1 → SW1 | 00D0.BA11.1111   | 0000.01AA.AAAA   |

| SW1 → R1  | 00D0.BA11.1111   | 0000.01AA.AAAA   |

| R1 → R2   | 0000.01BB.BBBB   | 0000.01CC.CCCC   |

| R2 → R3   | 0000.01DD.DDDD   | 0000.01EE.EEEE   |

| R3 → SW2  | 0000.01FF.FFFF   | 000C.8544.4444   |

| SW2 → PC4 | 0000.01FF.FFFF   | 000C.8544.4444   |



\## PC1 → PC3



| Segment   | Source MAC       | Destination MAC  |

| PC1 → SW1 | 00D0.BA11.1111   | 0010.1133.3333   |

| SW1 → PC3 | 00D0.BA11.1111   | 0010.1133.3333   |



\## PC4 → PC1



| Segment   | Source MAC       | Destination MAC  |

| PC4 → SW2 | 000C.8544.4444   | 0000.01FF.FFFF   |

| SW2 → R3  | 000C.8544.4444   | 0000.01FF.FFFF   |

| R3 → R2   | 0000.01EE.EEEE   | 0000.01DD.DDDD   |

| R2 → R1   | 0000.01CC.CCCC   | 0000.01BB.BBBB   |

| R1 → SW1  | 0000.01AA.AAAA   | 00D0.BA11.1111   |

| SW1 → PC1 | 0000.01AA.AAAA   | 00D0.BA11.1111   |



\## Key Findings



* Switches forward Ethernet frames using destination MAC addresses.
* Routers remove the incoming Layer 2 frame and create a new Ethernet frame for the next network segment.
* The source and destination MAC addresses therefore change at every routed hop.
* The IP packet remains end-to-end, while the Layer 2 frame is rebuilt at each hop.
* ARP is used to determine the MAC address of the next-hop device on the local segment.



\## Verification



Traffic was analyzed using:



* Cisco IOS CLI
* Packet Tracer Simulation Mode
* ARP information
* MAC address information



\## Skills Demonstrated



* Ethernet frame analysis
* MAC address analysis
* ARP
* Layer 2 switching
* Layer 3 routing
* Packet forwarding
* Cisco IOS CLI
* Packet Tracer Simulation Mode

