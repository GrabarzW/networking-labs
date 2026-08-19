\# Multilayer Switch Routing



\## Objective



Replace a Router-on-a-Stick configuration with Layer 3 routing on a

multilayer switch.



Configure Switch Virtual Interfaces (SVIs), a routed point-to-point

connection to R1, and a default route to provide inter-VLAN and Internet

connectivity.



\## Initial Configuration



The network was preconfigured with:



* Hosts assigned to the correct VLANs
* An SW1-SW2 trunk
* Router-on-a-Stick between R1 and SW2



SW2 was replaced with a multilayer switch for this lab.



\## Tasks



* Replace the R1-SW2 Router-on-a-Stick configuration with a point-to-point Layer 3 connection.
* Configure the Layer 3 connection using the IP addresses from the network diagram.
* Configure a default route on SW2 using R1 as the next hop.
* Configure one SVI on SW2 for each VLAN.
* Assign the last usable IP address of each subnet to the corresponding SVI.
* Verify inter-VLAN connectivity.
* Verify Internet connectivity by pinging `1.1.1.1`.



\## Concepts



* Multilayer switching
* Layer 3 switching
* Switch Virtual Interfaces (SVIs)
* Routed ports
* Inter-VLAN routing
* Default routes
* Next-hop routing
* Router-on-a-Stick vs. multilayer switching
* VLAN gateways
* Internet connectivity



\## Verification



Inter-VLAN connectivity was tested using ICMP ping between hosts in

different VLANs.



Internet connectivity was verified by pinging:



`1.1.1.1`



The routing configuration was also verified using Cisco IOS show commands.



\## Key Findings



* A multilayer switch can perform Layer 3 routing between VLANs without requiring Router-on-a-Stick.
* SVIs provide Layer 3 gateway interfaces for VLANs.
* A physical switch interface can be configured as a routed port for point-to-point Layer 3 connectivity.
* A default route allows SW2 to forward traffic for destinations outside its directly connected networks toward R1.
* Compared with Router-on-a-Stick, multilayer switching removes the need to route inter-VLAN traffic through multiple subinterfaces on a router.



\## Skills Demonstrated



* Cisco IOS CLI
* Multilayer switch configuration
* SVI configuration
* Routed port configuration
* Inter-VLAN routing
* Default route configuration
* Layer 3 network design
* Connectivity verification
* Cisco IOS troubleshooting

