\# Subnetting and VLSM



\## Objective



Subnet the `192.168.5.0/24` network using Variable Length Subnet Masking (VLSM)

to provide sufficient addressing for multiple LANs and a point-to-point

connection between R1 and R2.



Configure the resulting IPv4 networks and static routes to establish

end-to-end connectivity between all PCs.



\## Tasks



* Determine the addressing requirements for each network.
* Subnet `192.168.5.0/24` using VLSM.
* Allocate a separate subnet for each LAN.
* Allocate a subnet for the point-to-point connection between R1 and R2.
* Assign the first usable address to the PC in each LAN.
* Assign the last usable address to the router interface in each LAN.
* Configure IPv4 addresses on the PCs and routers.
* Configure static routes on each router.
* Verify connectivity between all PCs using ICMP ping.



\## Concepts



* IPv4 subnetting
* Variable Length Subnet Masking (VLSM)
* Network addresses
* Broadcast addresses
* Usable host ranges
* Subnet masks
* Point-to-point networks
* Static routing
* Routing tables
* End-to-end connectivity



\## Addressing Plan



The detailed VLSM addressing plan is documented in

addressing-table.xlsx .



\## Configuration



The first usable address of each LAN subnet was assigned to the

corresponding PC.



The last usable address of each LAN subnet was assigned to the

corresponding router interface.



A `/30` subnet was used for the point-to-point connection between R1

and R2.



Static routes were configured on R1 and R2 to provide reachability

between all LANs.



\## Verification



The configuration was verified using:



* `show ip interface brief`
* `show ip route`
* `ping`



ICMP connectivity was tested between all PCs to confirm end-to-end

reachability.



\## Skills Demonstrated



* IPv4 subnetting
* VLSM
* IPv4 address planning
* Cisco IOS CLI
* Static routing
* Routing table analysis
* Network configuration
* Network connectivity verification

