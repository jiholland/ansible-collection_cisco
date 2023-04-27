# Ansible Collection - jiholland.cisco

This collection includes helpful Ansible roles and content to help with Cisco network automation.

Roles included in this collection (click on the link to see the role's README and documentation):

  - `jiholland.cisco.backup`([documentation](https://github.com/jiholland/ansible-collection_cisco/blob/main/roles/backup/README.md))
  - `jiholland.cisco.banner`([documentation](https://github.com/jiholland/ansible-collection_cisco/blob/main/roles/banner/README.md))
  - `jiholland.cisco.interface_description`([documentation](https://github.com/jiholland/ansible-collection_cisco/blob/main/roles/interface_description/README.md))
  - `jiholland.cisco.tacacs`([documentation](https://github.com/jiholland/ansible-collection_cisco/blob/main/roles/tacacs/README.md))
  - `jiholland.cisco.upgrade`([documentation](https://github.com/jiholland/ansible-collection_cisco/blob/main/roles/upgrade/README.md))

## Installation

Install via Ansible Galaxy:

```yaml
ansible-galaxy collection install git@github.com:jiholland/ansible-collection_cisco.git
```

## Usage
```yaml
---
- name: Backup config from target to git.
  hosts: "{{ target }}"
  gather_facts: false

  roles:
    - role: jiholland.cisco.backup
      when: not ansible_check_mode
...

---
- name: Upgrade OS to compliant version.
  hosts: "{{ target }}"
  gather_facts: false

  roles:
    - jiholland.cisco.upgrade
...

---
- name: Ensure tacacs authentication.
  hosts: "{{ target }}"
  gather_facts: false

  roles:
    - jiholland.cisco.tacacs
...

---
- name: Set interface description based on CDP and LLDP.
  hosts: "{{ target }}"
  gather_facts: false

  roles:
    - jiholland.cisco.interface_description
...

---
- name: Ensure banner.
  hosts: "{{ target }}"
  gather_facts: false

  roles:
    - jiholland.cisco.banner
...
```
## License

BSD-3-Clause
