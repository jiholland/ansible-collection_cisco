💾 jiholland.backup
===================

Backup running-configuration to git repository.

Requirements
------------

💿 [Cisco IOS Collection](https://galaxy.ansible.com/cisco/ios)<br>
💿 [Cisco NXOS Collection](https://galaxy.ansible.com/cisco/nxos)<br>
💿 [Community General](https://galaxy.ansible.com/community/general)

Role Variables
--------------

- backup\_git\_repo
- backup\_git\_dest
- backup\_git\_version
- backup\_git\_accept\_newhostkey
- backup\_git\_config
- backup\_time
- backup\_cron\_weekday
- backup\_cron\_hour
- backup\_cron\_minute

Dependencies
------------

None.

Example Playbook
----------------
```yaml
---
- name: Backup config from target to git.
  hosts: "{{ target }}"
  gather_facts: false

  roles:
    - jiholland.cisco.backup
      when: not ansible_check_mode
```
📅 Use tag **backup_schedule** to schedule the backup using cron.

License
-------

BSD

Author Information
------------------

Jørn Ivar Holland
