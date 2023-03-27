# Ansible Collection - jiholland.cisco

This collection includes helpful Ansible roles and content to help with Cisco network automation.

Roles included in this collection (click on the link to see the role's README and documentation):

  - `jiholland.cisco.backup`([documentation](https://git@github.com:jiholland/ansible-collection_cisco/blob/main/roles/backup/README.md))
  - `jiholland.cisco.banner`([documentation](https://git@github.com:jiholland/ansible-collection_cisco/blob/main/roles/banner/README.md))
  - `jiholland.cisco.dhcp_snooping`([documentation](https://git@github.com:jiholland/ansible-collection_cisco/blob/main/roles/dns/README.md))
  - `jiholland.cisco.dns`([documentation](https://git@github.com:jiholland/ansible-collection_cisco/blob/main/roles/dns/README.md))
  - `jiholland.cisco.dot1x`([documentation](https://git@github.com:jiholland/ansible-collection_cisco/blob/main/roles/dns/README.md))
  - `jiholland.cisco.interface_description`([documentation](https://git@github.com:jiholland/ansible-collection_cisco/blob/main/roles/interface_description/README.md))
  - `jiholland.cisco.tacacs`([documentation](https://git@github.com:jiholland/ansible-collection_cisco/blob/main/roles/tacacs/README.md))
  - `jiholland.cisco.upgrade`([documentation](https://git@github.com:jiholland/ansible-collection_cisco/blob/main/roles/upgrade/README.md))

## Installation

Install via Ansible Galaxy:

```yaml
ansible-galaxy collection install git@github.com:jiholland/ansible-collection_cisco.git
```

## Usage
```yaml
---
- name: Upgrade OS to compliant version.
  hosts: "{{ target }}"
  gather_facts: false

  roles:
    - jiholland.cisco.upgrade
```

## License

BSD-3-Clause
