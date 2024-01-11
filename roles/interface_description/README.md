jiholland.interface_description
===============================

Set interface description based on CDP and LLDP.

Requirements
------------

💿 [Cisco IOS Collection](https://galaxy.ansible.com/ui/repo/published/cisco/ios)<br>
💿 [Cisco NXOS Collection](https://galaxy.ansible.com/ui/repo/published/cisco/nxos)<br>

Role Variables
--------------

- interface_description

Dependencies
------------

None.

Example Playbook
----------------
```YAML
---
- name: Set interface description based on CDP and LLDP
  gather_facts: false
  hosts: "{{ target }}"

  roles:
    - jiholland.cisco.interface_description
```
License
-------

BSD

Author Information
------------------

Jørn Ivar Holland
