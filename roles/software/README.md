🎚️ jiholland.software
=====================

Upgrade software on Cisco Catalyst and Nexus devices.

Requirements
------------

💿 [Cisco IOS Collection](https://galaxy.ansible.com/ui/repo/published/cisco/ios)<br>
💿 [Cisco NXOS Collection](https://galaxy.ansible.com/ui/repo/published/cisco/nxos)<br>

Role Variables
--------------

- software_version
- software_image
- software_vrf
- software_server
- software_path
- software_user
- software_password
- software_upload_bulk_mode
- software_upload_timeout
- software_issu
- software_install_timeout

Dependencies
------------

None.

Example Playbook
----------------
```yaml
---
- name: Upgrade software to compliant version.
  gather_facts: false
  hosts: "{{ target }}"
  strategy: ansible.builtin.free

  roles:
    - jiholland.cisco.software
```
🧪 Run playbook in check-mode to verify compliance without making any changes:

    ansible-playbook software_upgrade_playbook.yml -e "target=switch01" --check

🌱 Use tag **upload** to upload without installing:

    ansible-playbook software_upgrade_playbook.yml -e "target=switch01" --tags upload

💯 Run playbook without any tags to install immediately.


License
-------

BSD

Author Information
------------------

Jørn Ivar Holland
