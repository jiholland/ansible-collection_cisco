jiholland.dns
==============

Ensure DNS.

Requirements
------------

💿 [Cisco IOS Collection](https://galaxy.ansible.com/cisco/ios)<br>
💿 [Cisco NXOS Collection](https://galaxy.ansible.com/cisco/nxos)

Role Variables
--------------

- dns\_domain
- dns\_server\_primary
- dns\_server\_secondary

Dependencies
------------

None.

Example Playbook
----------------
```yaml
---
- name: Ensure DNS.
  hosts: "{{ target }}"
  gather_facts: false

  roles:
    - jiholland.cisco.dns
```
License
-------

BSD

Author Information
------------------

Jørn Ivar Holland
