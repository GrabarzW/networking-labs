\# VTP and DTP



\## Objective



Configure VLAN Trunking Protocol (VTP), trunk links, and Dynamic Trunking

Protocol (DTP) across multiple Cisco switches.



Analyze how VTP modes affect VLAN database synchronization and how DTP

settings affect trunk negotiation.



\## Network Configuration



The lab consists of three Cisco switches configured with different VTP modes:



| Switch |   VTP Mode  | VTP Domain |

|  SW1   |    Server   |    CCNA    |

|  SW2   | Transparent |    CCNA    |

|  SW3   |    Client   |    CCNA    |



\## Tasks



* Configure switch-to-switch connections as trunk ports.
* Disable DTP on trunk interfaces.
* Verify the administrative and operational mode of each trunk interface.
* Configure SW1 with the VTP domain `CCNA`.
* Create VLANs 10, 20, and 30 on SW1.
* Verify VLAN propagation to SW2 and SW3.
* Configure SW2 in VTP transparent mode.
* Create VLAN 40 on SW2.
* Verify whether VLAN 40 is propagated to SW1 and SW3.
* Configure SW3 in VTP client mode.
* Attempt to create VLAN 50 on SW3 and verify the result.
* Configure host-facing interfaces as manually configured access ports.
* Verify whether DTP remains enabled on the access ports.



\## Concepts



* VLAN Trunking Protocol (VTP)
* VTP server mode
* VTP client mode
* VTP transparent mode
* VTP domains
* VLAN database synchronization
* 802.1Q trunking
* Dynamic Trunking Protocol (DTP)
* Access ports
* Trunk ports
* Administrative mode
* Operational mode



\## Verification



The configuration was verified using Cisco IOS commands to inspect:



* VTP status and configuration
* VLAN databases
* Trunk interfaces
* Administrative and operational interface modes
* DTP status



VLAN propagation was tested by creating VLANs on switches operating

in different VTP modes.



\## Key Findings



* VTP can synchronize VLAN information between switches within the same VTP domain.
* VTP client switches receive VLAN information but cannot create VLANs ocally.
* VTP transparent switches maintain their own VLAN database and do not synchronize VLAN information in the same way as VTP clients.
* Trunk links are required to carry multiple VLANs between switches.
* DTP can negotiate trunking automatically unless it is manually disabled.
* Manually configuring access ports prevents them from dynamically negotiating trunking through DTP.



\## Skills Demonstrated



* Cisco IOS CLI
* VTP configuration
* VLAN management
* Trunk configuration
* DTP configuration
* Access port configuration
* VLAN database analysis
* Network configuration verification

