🪧 jiholland.banner
===================

Ensure banner for Cisco network-devices.

Requirements
------------

💿 [Cisco IOS Collection](https://galaxy.ansible.com/cisco/ios)<br>
💿 [Cisco NXOS Collection](https://galaxy.ansible.com/cisco/nxos)

Role Variables
--------------

None.

Dependencies
------------

None.

Example Playbook
----------------
```yaml
---
- name: Ensure banner.
  hosts: "{{ target }}"
  gather_facts: false

  roles:
    - jiholland.cisco.banner
```
License
-------

BSD

Author Information
------------------

Jørn Ivar Holland
