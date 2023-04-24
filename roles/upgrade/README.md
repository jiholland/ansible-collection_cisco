🎚️ jiholland.upgrade
====================

Upgrade OS, upload OS, schedule the upgrade or check OS compliance (see examples👇) for Cisco Catalyst and Nexus devices.

Requirements
------------

💿 [Cisco IOS Collection](https://galaxy.ansible.com/cisco/ios) <br>
💿 [Cisco NXOS Collection](https://galaxy.ansible.com/cisco/nxos) <br>
💿 [Ansible Posix Collection](https://galaxy.ansible.com/ansible/posix) <br>

Role Variables
--------------

- upgrade\_tftp\_server
- upgrade\_mgmt\_vrf
- upgrade\_compliance:
  - system
  - model
  - compliant\_version
  - compliant\_image

Dependencies
------------

None.

Example Playbook
----------------
```YAML
---
- name: Upgrade OS to compliant version.
  hosts: "{{ target }}"
  gather_facts: true

  roles:
    - jiholland.cisco.upgrade
```
🧪 Run playbook in check-mode to verify compliance without making any changes:

    ansible-playbook playbook_cisco_upgrade.yml -e "target=switch01" --check

🌱 Use tag **upload** to upload without installing:

    ansible-playbook playbook_cisco_upgrade.yml -e "target=switch01" --tags upload

📅 Use tag **schedule** to schedule the installation:

    ansible-playbook playbook_cisco_upgrade.yml -e "target=switch01" --tags schedule

💯 Run playbook without any tags to install immediately.


License
-------

BSD

Author Information
------------------

Jørn Ivar Holland
