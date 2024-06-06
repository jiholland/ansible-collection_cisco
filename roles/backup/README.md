💾 jiholland.backup
===================

Backup running-configuration to git repository.

Requirements
------------

💿 [Cisco IOS Collection](https://galaxy.ansible.com/ui/repo/published/cisco/ios)<br>
💿 [Cisco NXOS Collection](https://galaxy.ansible.com/ui/repo/published/cisco/nxos)<br>
💿 [Community General](https://galaxy.ansible.com/ui/repo/published/community/general)

Role Variables
--------------

- backup_temp_dir
- backup_git_repo
- backup_git_version
- backup_git_accept_newhostkey
- backup_git_config
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
  gather_facts: false
  hosts: "{{ target }}"
  roles:
    - role: jiholland.cisco.backup
      vars:
        backup_git_repo: git@gitlab.example.com:network-management/ansible-backup.git
```
📅 Use tag **backup_schedule** to schedule the backup using cron.

License
-------

BSD

Author Information
------------------

Jørn Ivar Holland=)
