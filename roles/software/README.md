🎚️ jiholland.software
=====================

Upgrade software on Cisco Catalyst and Nexus devices.

Requirements
------------

💿 [Cisco IOS Collection](https://galaxy.ansible.com/ui/repo/published/cisco/ios)<br>
💿 [Cisco NXOS Collection](https://galaxy.ansible.com/ui/repo/published/cisco/nxos)<br>
💿 [Ansible Posix Collection](https://galaxy.ansible.com/ui/repo/published/ansible/posix)<br>

Role Variables
--------------

- software_version
- software_image
- software_vrf
- software_server
- software_server_path
- software_server_user
- software_server_password
- software_upload_timeout
- software_install_timeout
- software_install_rescue_pause
- software_reboot_delay
- software_reboot_timeout
- software_playbook_name
- software_issu
- software_target

Dependencies
------------

None.

Example Playbook
----------------
```YAML
---
- name: Upgrade software to compliant version.
  gather_facts: true
  hosts: "{{ target }}"
  strategy: ansible.builtin.free

  roles:
    - jiholland.cisco.software
```
🧪 Run playbook in check-mode to verify compliance without making any changes:

    ansible-playbook playbook.yml -e "target=switch01" --check

🌱 Use tag **upload** to upload without installing:

    ansible-playbook playbook.yml -e "target=switch01" --tags upload

📅 Use tag **schedule** to schedule the installation:

    ansible-playbook playbook.yml -e "target=switch01" --tags schedule

💯 Run playbook without any tags to install immediately.


License
-------

BSD

Author Information
------------------

Jørn Ivar Holland
