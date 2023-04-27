🔍 jiholland.dhcp\_snooping
===========================

Ensure dhcp-snooping on access-layer switches.

Requirements
------------

💿 [Cisco IOS Collection](https://galaxy.ansible.com/cisco/ios)

Role Variables
--------------

None.

Dependencies
------------

None.

Example Playbook
----------------
```YAML
---
- name: Ensure dhcp snooping.
  hosts: "{{ target }}"
  gather_facts: false

  roles:
    - jiholland.cisco.dhcp_snooping
```
License
-------

BSD

Author Information
------------------

Jorn Ivar Holland
