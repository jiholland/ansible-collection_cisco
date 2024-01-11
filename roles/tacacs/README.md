jiholland.tacacs
================

Ensure tacacs authentication.

Requirements
------------

💿 [Cisco IOS Collection](https://galaxy.ansible.com/ui/repo/published/cisco/ios)<br>
💿 [Cisco NXOS Collection](https://galaxy.ansible.com/ui/repo/published/cisco/nxos)<br>

Role Variables
--------------

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
  gather_facts: false
  hosts: "{{ target }}"

  roles:
    - jiholland.cisco.tacacs
```
License
-------

BSD

Author Information
------------------

Jørn Ivar Holland
