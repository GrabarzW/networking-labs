\# EtherChannel



\## Objective



Configure and verify Layer 2 and Layer 3 EtherChannel using different negotiation methods and analyze EtherChannel load-balancing behavior.



The lab covers LACP, PAgP, static EtherChannel, trunking, Layer 3 port-channels, routing, and IP-based load balancing.



\## Tasks



1\. Configure a Layer 2 EtherChannel between ASW1 and DSW1 using LACP.

2\. Configure the EtherChannel as a trunk.

3\. Configure a Layer 2 EtherChannel between ASW2 and DSW2 using PAgP.

4\. Configure the EtherChannel as a trunk.

5\. Configure a Layer 3 EtherChannel between DSW1 and DSW2 using a static EtherChannel.

6\. Configure routing so that the PCs can reach SRV1.

7\. Identify the default EtherChannel load-balancing method on each switch.

8\. Configure EtherChannel load balancing based on source and destination IP addresses.



\## Network Design



| Connection  | EtherChannel Type | Protocol | Mode           |

| ----------- | ----------------- | -------- | -------------- |

| ASW1 – DSW1 | Layer 2           | LACP     | Negotiated     |

| ASW2 – DSW2 | Layer 2           | PAgP     | Negotiated     |

| DSW1 – DSW2 | Layer 3           | Static   | No negotiation |



The Layer 2 EtherChannels operate as trunks, while the DSW1–DSW2 EtherChannel operates at Layer 3.



\## Concepts



* EtherChannel
* Link aggregation
* Port-channel
* LACP
* PAgP
* Static EtherChannel
* Layer 2 EtherChannel
* Layer 3 EtherChannel
* 802.1Q trunking
* Port-channel interfaces
* Routing
* EtherChannel load balancing
* Source/destination hashing



\## Layer 2 EtherChannel — LACP



A Layer 2 EtherChannel was configured between:



\*\*ASW1 ↔ DSW1\*\*



LACP was used to negotiate the port-channel.



The resulting EtherChannel was configured as a trunk.



This allows multiple physical links to operate as a single logical Layer 2 connection while providing increased aggregate bandwidth and link redundancy.



\## Layer 2 EtherChannel — PAgP



A second Layer 2 EtherChannel was configured between:



\*\*ASW2 ↔ DSW2\*\*



This EtherChannel uses Cisco PAgP for negotiation.



The resulting port-channel was also configured as a trunk.



\## Layer 3 EtherChannel



A Layer 3 EtherChannel was configured between:



\*\*DSW1 ↔ DSW2\*\*



Unlike the access-layer EtherChannels, this port-channel operates at Layer 3 using a static EtherChannel configuration.



Routing was then configured to provide connectivity between the PCs and SRV1.



\## Default Load-Balancing Method



The default EtherChannel load-balancing method observed on the switches was:



| Switch | Default Method |

| ------ | -------------- |

| ASW1   | Source MAC     |

| DSW1   | Source MAC     |

| ASW2   | Source MAC     |

| DSW2   | Source MAC     |



\## IP-Based Load Balancing



The switches were configured to use source and destination IP addresses for EtherChannel load balancing.



This changes how traffic is distributed across the physical links belonging to the port-channel.



The EtherChannel remains a single logical interface, while the hashing algorithm determines which physical member link carries a particular traffic flow.



\## Verification



Useful Cisco IOS commands:



```text

show etherchannel summary

show interfaces trunk

show etherchannel load-balance

show ip interface brief

show ip route

channel-group 'number' mode 'mode'

```



These commands can be used to verify:



* Port-channel formation
* LACP/PAgP operation
* Layer 2 vs Layer 3 EtherChannel
* Trunk configuration
* Member interfaces
* EtherChannel load-balancing method
* Routing configuration
* End-to-end connectivity



\## Key Findings



* EtherChannel combines multiple physical interfaces into one logical port-channel.
* LACP provides standards-based EtherChannel negotiation.
* PAgP is Cisco's EtherChannel negotiation protocol.
* Static EtherChannel does not use a negotiation protocol.
* Layer 2 EtherChannels can operate as trunks.
* Layer 3 EtherChannels can provide routed connectivity between multilayer switches.
* EtherChannel provides redundancy because traffic can continue using remaining member links if one physical link fails.
* Load balancing determines which physical member link carries each traffic flow.
* Source/destination IP hashing can distribute routed traffic based on Layer 3 addressing.



\## Skills Demonstrated



* Cisco IOS CLI
* EtherChannel configuration
* LACP
* PAgP
* Static EtherChannel
* Layer 2 port-channels
* Layer 3 port-channels
* 802.1Q trunking
* Routing
* EtherChannel load balancing
* Port-channel verification
* Redundancy and link aggregation
* Network connectivity troubleshooting



