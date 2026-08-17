\# VLAN Configuration



\## Objective



Configure and organize a Cisco switch using multiple VLANs and assign

network devices to the appropriate broadcast domains.



Use Packet Tracer Simulation Mode to analyze how VLAN segmentation

affects network traffic.



\## Network Segmentation



The network is divided into three VLANs:



| VLAN |     Name    |       Purpose       |

|  10  | Engineering | Engineering devices |

|  20  |      HR     |      HR devices     |

|  30  |    Sales    |     Sales devices   |



\## Tasks



* Configure the correct IPv4 address and subnet mask on each PC.
* Configure the default gateway as the last usable address of each subnet.
* Create and name the required VLANs on SW1.
* Assign switch interfaces to the appropriate VLANs.
* Configure the switch interfaces connected to R1 for the appropriate VLANs.
* Configure the R1 interfaces associated with each VLAN.
* Verify connectivity between the PCs.
* Generate broadcast traffic from a PC.
* Analyze broadcast propagation using Packet Tracer Simulation Mode.



\## Concepts



* VLANs
* VLAN identification
* Access ports
* VLAN membership
* Layer 2 segmentation
* Broadcast domains
* IPv4 addressing
* Default gateways
* Broadcast traffic



\## Verification



Connectivity between the PCs was tested using ICMP ping.



Broadcast traffic was analyzed using Packet Tracer Simulation Mode to

determine which devices receive broadcasts within each VLAN.



\## Key Findings



* Each VLAN creates a separate Layer 2 broadcast domain.
* Devices assigned to different VLANs are isolated at Layer 2.
* Broadcast traffic remains within its originating VLAN.
* Switch ports must be assigned to the correct VLAN for devices to communicate within the intended broadcast domain.
* A Layer 3 gateway is required for communication between different VLANs.



\## Skills Demonstrated



* Cisco IOS CLI
* VLAN creation and configuration
* VLAN naming
* Switch port configuration
* IPv4 addressing
* Broadcast domain analysis
* Network segmentation
* Packet Tracer Simulation Mode

