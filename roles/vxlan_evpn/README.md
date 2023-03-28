🏭 jiholland.vxlan\_evpn
========================

Configure multisite VXLAN-EVPN fabric on Cisco Nexus platform.

**Underlay:**
- OSPF routing.
- P2P L3 links.
- PIM Sparse with Anycast RP.
```YAML
                       OSPF AREA 0.0.0.0
       + - - - - - - - - - - - - - - - - - - - - - - -
       |         PIM Anycast RP (Loopback254)         |
       + - - - - - - - - - - - - - - - - - - - - - - -
       +--------------------+    +--------------------+
       |      SPINE-1       |    |      SPINE-2       |
       | RID: 10.250.250.30 |    | RID: 10.250.250.31 |
       +--------------------+    +--------------------+
                | |                       | |
           +-+--+-+-----------------------+ |
           | |  +---------Loopback0---------+-----+-+
           | |                                    | |
+--------------------+                            | |
|       LEAF-1       |                 +------------+-------+
| RID: 10.250.250.32 |                 |       LEAF-2       |
+--------------------+                 | RID: 10.250.250.33 |
                                       +--------------------+
```
**Overlay:**
- iBGP EVPN control plane.
- Multicast-replication (BUM).
```YAML
                         BGP ASN 65001
        +--------------------+   +--------------------+
        |      SPINE-1       |   |      SPINE-2       |
        | RID: 10.250.250.30 |   | RID: 10.250.250.31 |
        +--------------------+   +--------------------+
                   | |                      | |
           +-+-----+-+----------------------+ |
           | |     +--------Loopback0---------+----+-+
           | |                                     | |
+--------------------+                             | |
|       LEAF-1       |                  +--------------------+
| RID: 10.250.250.32 |                  |       LEAF-2       |
+--------------------+                  | RID: 10.250.250.33 |
+ - - - - - - - - - -                   +--------------------+
         VTEP        |                  + - - - - - - - - - -
|     Loopback1                                  VTEP        |
   10.254.250.32/32  |                  |     Loopback1
|                                          10.254.250.33/32  |
 - - - - - - - - - - +                  + - - - - - - - - - -
+ - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
                 Distributed Anycast Gateway                 |
|                    GW IP: 172.16.100.1
                    GW MAC: 2020.DEAD.BEEF                   |
+ - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
```
**DCI:**
- Border-leafs in vPC.
- eBGP in DCI underlay and overlay.
- Ingress-replication (BUM).
- MACsec encryption (dark-fiber).

**L2 Host Segment:**
```YAML
+--------------+                             +--------------+
|    LEAF-1    |         VNI 10100           |    LEAF-2    |
|     VTEP     |---------------------------->|     VTEP     |
+--------------+                             +--------------+
        ^                                            |
        |                                            |
        | VLAN 100                         VLAN 100  v
+---------------+                            +---------------+
|    HOST-A     |                            |    HOST-B     |
|172.16.100.2/24| HOST-A$ ping 172.16.100.3  |172.16.100.3/24|
|   VLAN 100    |- - - - - - - - - - - - - ->|   VLAN 100    |
|   VNI 10100   |                            |   VNI 10100   |
+---------------+                            +---------------+
```
**L3 Host Segment:**
- Distributed anycast gateway.
- Multi-tenancy (VRFs).
- ARP suppression at leafs.
```YAML
                        VRF Tenant-1
                        L3 VNI 10010
+--------------+                            +--------------+ 
|    LEAF-1    |         VNI 10010          |    LEAF-2    | 
|     VTEP     |--------------------------->|     VTEP     | 
+--------------+                            +--------------+ 
        ^                                           |        
        |                                           |        
        | VLAN 100                         VLAN 101 v        
+---------------+                           +---------------+
|    HOST-A     |                           |    HOST-C     |
|172.16.100.2/24| HOST-A$ ping 172.16.101.2 |172.16.101.2/24|
|   VLAN 100    |- - - - - - - - - - - - - >|   VLAN 101    |
|   VNI 10100   |                           |   VNI 10101   |
+---------------+                           +---------------+
```
**Broadcast, Unknown Unicast, Multicast:**
- Note: BUM between sites (dci) are always ingress-replicated (unicast).
```YAML
                     + - - - - - - -
                      PIM Anycast RP|
                     + - - - - - - -
                     +--------------+
                     |   SPINE-1    |
                     +--------------+
                            ^ |  |
                            | |  +--------------239.0.0.2---------------+
                            | |                                         |
+-----+ +------239.0.0.1----+ +----239.0.0.1--------+ +-----+           |
|2.ARP| |                                           | |3.ARP|   +--------------+
+-----+ |                                           | +-----+   |    LEAF-3    |
        |                                           v           |     VTEP     |
+--------------+                            +--------------+    +--------------+
|    LEAF-1    |         VNI 10100          |    LEAF-2    |            |
|     VTEP     |--------------------------->|     VTEP     |            |
+--------------+                            +--------------+            |
        ^                                           |                   |
+-----+ |                                           | +-----+           |
|1.ARP| |                                           | |4.ARP|           |
+-----+ |                                           v +-----+           |
+---------------+                           +---------------+   +---------------+
|    HOST-A     | HOST-A$ ping 172.16.100.3 |    HOST-B     |   |    HOST-C     |
|172.16.100.2/24|   (MAC unknown --> ARP)   |172.16.100.3/24|   |172.16.101.2/24|
|   VLAN 100    |- - - - - - - - - - - - - >|   VLAN 100    |   |   VLAN 101    |
|   VNI 10100   |                           |   VNI 10100   |   |   VNI 10101   |
|Mcast 239.0.0.1|                           |Mcast 239.0.0.1|   |Mcast 239.0.0.2|
+---------------+                           +---------------+   +---------------+
```

📚**Resources:**<br>
- [Cisco Nexus VXLAN configuration guide](https://www.cisco.com/c/en/us/td/docs/dcn/nx-os/nexus9000/102x/configuration/vxlan/cisco-nexus-9000-series-nx-os-vxlan-configuration-guide-release-102x.html)<br>
- [Cisco VXLAN-EVPN Multi-Site Design and Deployment whitepaper](https://www.cisco.com/c/en/us/products/collateral/switches/nexus-9000-series-switches/white-paper-c11-739942.html#Introduction)<br>
- [Ansible documentation for Cisco Nexus](https://docs.ansible.com/ansible/latest/collections/cisco/nxos/index.html)<br>

Requirements
------------

💿 [Cisco NXOS Collection](https://galaxy.ansible.com/cisco/nxos)<br>

Role Variables
--------------

defaults/main.yml:
- vxlan\_evpn\_pim\_anycast\_rp\_ip
- vxlan\_evpn\_pim\_group\_range
- vxlan\_evpn\_bgp\_neighbors
- vxlan\_evpn\_nve\_infra\_vlan\_id
- vxlan\_evpn\_dci\_macsec\_key
- vxlan\_evpn\_features
- vxlan\_evpn\_mtu
- vxlan\_evpn\_ospf\_area\_id
- vxlan\_evpn\_ospf\_process\_id
- vxlan\_evpn\_anycast\_gw\_mac
- vxlan\_evpn\_rid\_loopback
- vxlan\_evpn\_vtep\_loopback
- vxlan\_evpn\_dci\_loopback
- vxlan\_evpn\_pim\_loopback
- vxlan\_evpn\_rmap\_host\_svi\_name
- vxlan\_evpn\_rmap\_host\_svi\_tag

hostvars/spine.yml:
- network\_function
- bgp\_asn
- rid\_ip
- bgp\_route\_reflector: true

hostvars/leaf.yml:
- network\_function
- bgp\_asn
- rid\_ip

hostvars/border-leaf.yml:
- network\_function
- bgp\_asn
- rid\_ip
- bgp\_route\_reflector: true
- vtep\_vpc\_vip
- nve\_infra\_ip
- dci\_vip
- dci\_interfaces
  - name
  - ip
  - bgp\_neighbor\_ip
  - bgp\_neighbor\_name
  - bgp\_remote\_asn

Dependencies
------------

💿 [jiholland.vpc](https://github.com/jiholland/ansible-collection_cisco/tree/main/roles/vpc)

Example Playbook
----------------
```YAML
---
- name: Build VXLAN-EVPN fabric.
  hosts: "{{ target }}"
  gather_facts: false

  roles:

    - role: jiholland.cisco.vpc
      when: vpc_domain is defined

    - role: jiholland.cisco.vxlan_evpn
```
License
-------

BSD

Author Information
------------------

Jørn Ivar Holland
