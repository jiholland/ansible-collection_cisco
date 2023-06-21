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

- backup_git_repo
- backup_git_dest
- backup_git_version
- backup_git_accept_newhostkey
- backup_git_config
- backup_time
- backup_cron_weekday
- backup_cron_hour
- backup_cron_minute

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
