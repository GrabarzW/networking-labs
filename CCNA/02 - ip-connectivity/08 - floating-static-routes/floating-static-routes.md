# Floating Static Routes

## Objective

Identify the dynamic routing protocol used in the network and configure floating static routes as a backup path between PC1 and SRV1 in case the primary link fails.

## Tasks

1. Check the routing tables of R1 and R2 and identify the dynamic routing protocol used by Enterprise A.
2. Identify which routes are used when PC1 accesses SRV1 and the remote server at `1.1.1.1`.
3. Configure floating static routes on R1 and R2 to provide an alternative path to SRV1 if the R1–R2 link fails.
4. Verify whether the floating static routes are installed in the routing tables while the primary path is available.
5. Shut down the `G0/2/0` interface on R1 or R2 and verify that the floating static routes become active.
6. Ping SRV1 from PC1 to confirm connectivity after the primary path fails.

## Concepts

* Dynamic routing
* Static routing
* Floating static routes
* Administrative Distance
* Route selection
* Network failover

## Configuration

Floating static routes were configured with a higher Administrative Distance than the dynamically learned routes. This allows the dynamic routes to remain preferred while the primary path is available.

When the primary route becomes unavailable, the floating static route can be installed in the routing table and used as a backup path.

## Verification

Useful Cisco IOS commands:

```text
show ip route
ping <destination>
```

The following command is used to configure a floating static route:

```text
ip route <network> <subnet-mask> <next-hop> <administrative-distance>
```

The primary interface can be disabled to simulate a link failure:

```text
shutdown
```

## Results / Observations

* Enterprise A uses OSPF as its dynamic routing protocol.
* PC1 reaches SRV1 using 10.0.0.2 while the primary link is available.
* PC1 reaches `1.1.1.1` using 203.0.113.9.
* The floating static routes are `[not installed / installed]` while the primary dynamic routes are available.
* After shutting down `G0/2/0`, the floating static routes were installed in the routing tables.
* PC1 could reach SRV1 after the primary link failed.

## Key Findings

* A floating static route uses a higher Administrative Distance than the preferred route.
* The floating static route is used as a backup when the preferred route becomes unavailable.
* This provides an alternative path and improves network resilience during a link failure.

## Skills Demonstrated

* Cisco IOS CLI
* Dynamic routing
* Static route configuration
* Floating static routes
* Administrative Distance
* Routing table analysis
* Network failover
* Connectivity troubleshooting
