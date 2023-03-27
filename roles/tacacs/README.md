🅰️🅰️🅰️ jiholland.tacacs
=======================

Ensure tacacs authentication.

Requirements
------------

[Cisco IOS Collection](https://galaxy.ansible.com/cisco/ios)<br>
[Cisco NXOS Collection](https://galaxy.ansible.com/cisco/nxos)

Role Variables
--------------

- tacacs\_server\_group
- tacacs\_server\_key
- tacacs\_server\_primary\_name
- tacacs\_server\_primary\_ip
- tacacs\_server\_secondary\_name
- tacacs\_server\_secondary\_ip

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
