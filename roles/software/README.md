🎚️ jiholland.software
=====================

Upgrade software on Cisco Catalyst and Nexus devices.

Requirements
------------

💿 [Cisco IOS Collection](https://galaxy.ansible.com/cisco/ios) <br>
💿 [Cisco NXOS Collection](https://galaxy.ansible.com/cisco/nxos) <br>
💿 [Ansible Posix Collection](https://galaxy.ansible.com/ansible/posix) <br>

Role Variables
--------------

- software_tftp_server
- software_upload_timeout
- software_install_timeout
- software_install_issu_timeout
- software_install_rescue_timeout
- software_reboot_delay
- software_reboot_timeout
- software_playbook_name
- software_version
- software_image
- software_vrf
- software_issu

Dependencies
------------

None.

Example Playbook
----------------
```yaml
---
- name: Upgrade software to compliant version.
  hosts: "{{ target }}"
  strategy: linear
  gather_facts: true

  roles:
    - jiholland.cisco.software
```
🧪 Run playbook in check-mode to verify compliance without making any changes:

    ansible-playbook playbook_software_upgrade.yml -e "target=switch01" --check

🌱 Use tag **upload** to upload without installing:

    ansible-playbook playbook_software_upgrade.yml -e "target=switch01" --tags upload

📅 Use tag **schedule** to schedule the installation:

    ansible-playbook playbook_software_upgrade.yml -e "target=switch01" --tags schedule

💯 Run playbook without any tags to install immediately.


License
-------

BSD

Author Information
------------------

Jørn Ivar Holland
