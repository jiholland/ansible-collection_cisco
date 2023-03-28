👯 jiholland.vpc
================

Configure a pair of Cisco Nexus devices in virtual Port Channel (vPC).

Requirements
------------

💿 [Cisco NXOS Collection](https://galaxy.ansible.com/cisco/nxos)

Role Variables
--------------

defaults:
- vpc\_keepalive\_vrf
- vpc\_delay\_restore
- vpc\_svi\_delay\_restore
- vpc\_native\_vlan\_id
- vpc\_native\_vlan\_name

hostvars:
- vpc\_domain
- vpc\_role\_priority
- vpc\_keepalive\_ip
- vpc\_keepalive\_ip\_peer
- vpc\_keepalive\_if
- vpc\_peer\_portchannel\_id
- vpc\_peer\_portchannel\_if\_member\_1
- vpc\_peer\_portchannel\_if\_member\_2

Dependencies
------------

None.

Example Playbook
----------------
```YAML
---
- name: Configure a pair of Cisco Nexus devices in vPC.
  hosts: "{{ target }}"
  gather_facts: false

  roles:
    - jiholland.cisco.vpc
```
License
-------

BSD

Author Information
------------------

Jørn Ivar Holland
