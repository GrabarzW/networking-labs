\# EIGRP Configuration



\## Objective



Configure EIGRP on all routers, establish dynamic routing using loopback and physical interfaces, and enable unequal-cost load balancing on R1 for traffic destined for `192.168.4.0/24`.



\## Tasks



1\. Configure hostnames and IP addresses on all devices.

2\. Configure a loopback interface on each router.

3\. Configure EIGRP on all routers and enable it on the appropriate interfaces.

4\. Disable EIGRP auto-summary.

5\. Configure passive interfaces where appropriate, including loopback interfaces.

6\. Configure unequal-cost load balancing on R1 using the `variance` command for traffic destined for `192.168.4.0/24`.

7\. Verify EIGRP operation and routing table entries.



\## Concepts



\- EIGRP

\- Dynamic routing

\- Loopback interfaces

\- Passive interfaces

\- Automatic route summarization

\- EIGRP metric

\- Unequal-cost load balancing

\- Variance



\## Configuration



\### EIGRP



EIGRP was configured on all routers to exchange routing information. Auto-summary was disabled to prevent unwanted automatic summarization of routes.



\### Loopback Interfaces



A loopback interface was configured on each router using a unique `/32` IPv4 address. The loopback interfaces were included in EIGRP.



\### Passive Interfaces



Passive interfaces were configured where EIGRP neighbor relationships were not required. This included loopback interfaces and appropriate LAN-facing interfaces.



\### Unequal-Cost Load Balancing



The `variance` command was configured on R1 with a value of `2` to allow eligible unequal-cost routes to be used for traffic destined for `192.168.4.0/24`.



\## Verification



Useful Cisco IOS commands:



```text

show ip protocols

show ip interface brief

show ip route

show ip eigrp neighbors

show ip eigrp topology

```



These commands can be used to verify EIGRP configuration, interface status, established neighbor relationships, routing table entries, and available EIGRP paths.



\## Key Findings



\- EIGRP exchanges routing information between routers and selects paths using its composite metric.

\- Passive interfaces prevent EIGRP neighbor relationships from forming through those interfaces while allowing appropriate network advertisements.

\- Disabling auto-summary helps preserve more specific network prefixes.

\- The `variance` command allows eligible unequal-cost paths to be considered for load balancing when they satisfy EIGRP's route-selection conditions.



\## Skills Demonstrated



\- Cisco IOS CLI

\- EIGRP configuration and verification

\- Dynamic routing

\- Loopback interface configuration

\- Passive interface configuration

\- Routing table analysis

\- EIGRP metric and variance

\- Unequal-cost load balancing



