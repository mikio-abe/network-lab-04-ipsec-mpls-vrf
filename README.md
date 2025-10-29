# IPsec over MPLS VPN with VRF

![Topology](topology.jpg)

## Summary

Site-to-site VPN over ISP MPLS backbone with VRF-aware IPsec at PE-CE boundaries. PE routers exchange routes via BGP VPNv4 while MPLS provides label switching in the provider core.

## Lab Environment

**Emulation Platform:**
- Hypervisor: VMware Workstation Pro
- Network Emulator: EVE-NG Community Edition
- Base OS: Ubuntu 22.04 LTS
- Router Platform: Cisco IOL (IOS on Linux)
- IOS Version: 15.x

**Topology:**
See topology.png for network diagram and device connections.

All configurations have been tested and verified in this environment.

## 📁 Lab Files

**EVE-NG Topology File:** [Download 3IPSEC-MPLS-VPN.unl](https://raw.githubusercontent.com/mikio-abe/network-lab-04-ipsec-mpls-vrf/main/3IPSEC-MPLS-VPN.unl)

Right-click the link above and select "Save Link As..." to download the complete EVE-NG lab topology file.

### Configuration Files:
- [CE1.cfg](https://raw.githubusercontent.com/mikio-abe/network-lab-04-ipsec-mpls-vrf/main/CE1.cfg) - Customer Edge 1 (AS 65000)
- [CE2.cfg](https://raw.githubusercontent.com/mikio-abe/network-lab-04-ipsec-mpls-vrf/main/CE2.cfg) - Customer Edge 2 (AS 65002)
- [PE1.cfg](https://raw.githubusercontent.com/mikio-abe/network-lab-04-ipsec-mpls-vrf/main/PE1.cfg) - Provider Edge 1 (VRF + MP-BGP + MPLS)
- [PE2.cfg](https://raw.githubusercontent.com/mikio-abe/network-lab-04-ipsec-mpls-vrf/main/PE2.cfg) - Provider Edge 2 (VRF + MP-BGP + MPLS)
  
## Verification

```
show crypto isakmp sa
show ip route vrf ISP_A
show bgp vpnv4 unicast vrf ISP_A
ping vrf ISP_A 192.168.2.1 source 192.168.1.1
```

**Blog:** [Medium Article](https://medium.com/@miki2013smp/ai-assisted-mpls-vpn-learning-from-standard-configuration-to-production-scenarios-9f8a88b4c2c3)
