# Verification Commands

## IPsec
Check Phase 1/2 status and encrypted packet count
```
show crypto isakmp sa
show crypto ipsec sa | include pkts
show interface tunnel10
```

## VRF
Check VRF configuration and routing table
```
show ip vrf
show ip route vrf ISP_A
```

## MPLS
Check LDP neighbor and label forwarding
```
show mpls ldp neighbor
show mpls forwarding-table vrf ISP_A
```

## BGP
Check VPNv4 route exchange
```
show bgp vpnv4 unicast vrf ISP_A
show ip bgp vpnv4 vrf ISP_A 192.168.2.0
```

## Connectivity
Test end-to-end connectivity
```
ping 192.168.2.1 source 192.168.1.1
ping vrf ISP_A 192.168.2.1 source 192.168.1.1
```
