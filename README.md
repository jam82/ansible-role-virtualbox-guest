# ansible-role-virtualbox-guest

**Ansible role for setting up [VirtualBox](https://virtualbox.org) guest additions.**

Besides from installing guest additions to any vm, this role is also meant to be used together with [packer](https://packer.io), why it may seem a bit overcomplicated...

## Supported Platforms

- Alpine 3.11
- Archlinux
- CentOS 8
- Debian 9, 10
- Fedora 31
- OpenSuse Leap 15.x
- Ubuntu 18.04, 20.04

## Requirements

Ansible 2.9 or higher is recommended.

## Variables

Variables and defaults for this role:

```yaml
---
# role: ansible-role-virtualbox-guest
# file: defaults/main.yml

# The role is disabled by default, so you do not get in trouble.
# Checked in tasks/main.yml which includes tasks.yml if enabled.
virtualbox_guest_role_enabled: False

# Reboot the machine after VirtualBox guest additions installation.
virtualbox_guest_reboot: False
```

## Dependencies

None.

## Example Playbook

```yaml
---
# role: ansible-role-virtualbox-guest
# file: site.yml

- hosts: virtualbox_guest_systems
  become: True
  vars:
    virtualbox_guest_role_enabled: True
  roles:
    - role: ansible-role-virtualbox-guest
```

## License and Author

- Author:: [jam82](https://github.com/jam82/)
- Copyright:: 2020, [jam82](https://github.com/jam82/)

Licensed under [MIT License](https://opensource.org/licenses/MIT).
See [LICENSE](https://github.com/jam82/ansible-role-virtualbox-guest/blob/master/LICENSE) file in repository.

## References

- [ArchWiki](https://wiki.archlinux.org/index.php/VirtualBox#Install_the_Guest_Additions)
