🅰️🅰️🅰️ jiholland.tacacs
====================

Ensure tacacs authentication.

Requirements
------------

[Cisco IOS Collection](https://galaxy.ansible.com/cisco/ios)<br>
[Cisco NXOS Collection](https://galaxy.ansible.com/cisco/nxos)

Role Variables
--------------

- tacacs_file
- tacacs_group
- tacacs_servers
- tacacs_key
- tacacs_source_interface
- tacacs_vrf

Dependencies
------------

None.

Example Playbook
----------------
```YAML
---
- name: Ensure tacacs authentication.
  hosts: "{{ target }}"
  gather_facts: false

  roles:
    - jiholland.cisco.tacacs
```
License
-------

BSD

Author Information
------------------

Jørn Ivar Holland
