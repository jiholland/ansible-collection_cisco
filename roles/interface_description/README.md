jiholland.interface_description
================================

Set interface description based on CDP and LLDP.

Requirements
------------

💿 [Cisco IOS Collection](https://galaxy.ansible.com/cisco/ios)<br>
💿 [Cisco NXOS Collection](https://galaxy.ansible.com/cisco/nxos)

Role Variables
--------------

- interface_description

Dependencies
------------

None.

Example Playbook
----------------
```yaml
---
- name: Set interface description based on CDP and LLDP
  hosts: "{{ target }}"
  gather_facts: false

  roles:
    - jiholland.cisco.interface_description
```
License
-------

BSD

Author Information
------------------

Jørn Ivar Holland
