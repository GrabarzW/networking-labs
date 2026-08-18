\# VLAN Trunking and Router-on-a-Stick



\## Objective



Configure VLANs across multiple switches and establish inter-VLAN

connectivity using an 802.1Q trunk and Router-on-a-Stick.



\## Network Configuration



The network consists of two switches connected by an 802.1Q trunk.

The second switch is connected to R1, which provides Layer 3 gateways

for the VLANs using router subinterfaces.



\## Tasks



* Configure PC-facing switch interfaces as access ports.
* Assign access ports to the appropriate VLANs.
* Configure the SW1-SW2 connection as a trunk.
* Allow only the required VLANs on the trunk.
* Configure an unused VLAN as the native VLAN.
* Ensure all required VLANs exist on both switches.
* Configure the SW2-R1 connection for Router-on-a-Stick.
* Create router subinterfaces for the required VLANs.
* Configure the last usable address of each subnet on the corresponding router subinterface.
* Verify connectivity between all PCs using ICMP ping.



\## Concepts



* VLANs
* Access ports
* 802.1Q trunking
* Native VLAN
* Allowed VLANs
* VLAN propagation between switches
* Router-on-a-Stick
* Router subinterfaces
* Inter-VLAN routing
* Broadcast domains



\## Verification



Connectivity between all PCs was verified using ICMP ping.



The configuration was also verified to ensure that:



* Required VLANs exist on both switches.
* Only required VLANs are allowed across the SW1-SW2 trunk.
* The native VLAN is configured correctly.
* Router subinterfaces are associated with the correct VLANs.
* All PCs can communicate with each other.



\## Key Findings



* Access ports carry traffic for a single VLAN.
* Trunk ports can carry traffic for multiple VLANs.
* 802.1Q tagging allows switches to identify the VLAN associated with each frame traversing a trunk.
* The native VLAN carries untagged traffic on an 802.1Q trunk.
* Router-on-a-Stick uses multiple router subinterfaces over a single physical router interface to provide Layer 3 connectivity between VLANs.
* VLANs remain separate Layer 2 broadcast domains while the router provides communication between them.



\## Skills Demonstrated



* Cisco IOS CLI
* VLAN configuration
* Access port configuration
* 802.1Q trunk configuration
* Native VLAN configuration
* Allowed VLAN configuration
* Router subinterface configuration
* Router-on-a-Stick
* Inter-VLAN routing
* Network connectivity verification

