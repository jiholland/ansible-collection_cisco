🔐 jiholland.dot1x
===================

Configure 802.1X.

Requirements
------------

💿 [Cisco IOS Collection](https://galaxy.ansible.com/cisco/ios)

Role Variables
--------------

- dot1x\_server\_group
- dot1x\_server\_key
- dot1x\_server\_primary\_name
- dot1x\_server\_primary\_ip
- dot1x\_server\_secondary\_name
- dot1x\_server\_secondary\_ip
- dot1x\_interface\_authentication\_order
- dot1x\_interface\_authentication\_priority
- dot1x\_interface\_authentication\_multi\_auth
- dot1x\_radius\_server\_attributes
- dot1x\_device\_sensors

Dependencies
------------

None.

Example Playbook
----------------
```YAML
---
- name: Configure 802.1X.
  hosts: "{{ target }}"
  gather_facts: true

  roles:
    - jiholland.network.dot1x
```
License
-------

BSD

Author Information
------------------

Jørn Ivar Holland
