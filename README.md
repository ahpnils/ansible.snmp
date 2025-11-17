# Ansible Role: SNMP

[![ansible-lint.yml](https://github.com/ahpnils/ansible.snmp/actions/workflows/ansible-lint.yml/badge.svg)](https://github.com/ahpnils/ansible.snmp/actions/workflows/ansible-lint.yml)
[![ansible-test.yml](https://github.com/ahpnils/ansible.snmp/actions/workflows/ansible-test.yml/badge.svg)](https://github.com/ahpnils/ansible.snmp/actions/workflows/ansible-test.yml)
[![codespell.yml](https://github.com/ahpnils/ansible.snmp/actions/workflows/codespell.yml/badge.svg)](https://github.com/ahpnils/ansible.snmp/actions/workflows/codespell.yml)
[![markdownlint.yml](https://github.com/ahpnils/ansible.snmp/actions/workflows/markdownlint.yml/badge.svg)](https://github.com/ahpnils/ansible.snmp/actions/workflows/markdownlint.yml)
[![qemu-kvm-integration-tests.yml](https://github.com/ahpnils/ansible.snmp/actions/workflows/qemu-kvm-integration-tests.yml/badge.svg)](https://github.com/ahpnils/ansible.snmp/actions/workflows/qemu-kvm-integration-tests.yml)
[![shellcheck.yml](https://github.com/ahpnils/ansible.snmp/actions/workflows/shellcheck.yml/badge.svg)](https://github.com/ahpnils/ansible.snmp/actions/workflows/shellcheck.yml)
[![tft.yml](https://github.com/ahpnils/ansible.snmp/actions/workflows/tft.yml/badge.svg)](https://github.com/ahpnils/ansible.snmp/actions/workflows/tft.yml)
[![tft_citest_bad.yml](https://github.com/ahpnils/ansible.snmp/actions/workflows/tft_citest_bad.yml/badge.svg)](https://github.com/ahpnils/ansible.snmp/actions/workflows/tft_citest_bad.yml)
[![woke.yml](https://github.com/ahpnils/ansible.snmp/actions/workflows/woke.yml/badge.svg)](https://github.com/ahpnils/ansible.snmp/actions/workflows/woke.yml)

## Description

Ansible role for installing and Configuration SNMP v3 on installs RHEL/CentOS or Debian/Ubuntu and SNMP v2 on Windows.

## Installation

```bash
ansible-galaxy install ahpnils.snmp
```

## Requirements

## Role Variables

| Variable                       | Default                                                                 | Comments (type)                                 |
| :----------------------------- | :---------------------------------------------------------------------- | :---------------------------------------------- |
| snmp_user                      | snmp                                                                    | SNMP User                                       |
| snmp_password                  | snmp_password                                                           | SNMP Password                                   |
| snmp_encryption                | snmp_encryption                                                         | SNMP Encryption                                 |
| snmp_contact                   |                                                                         | Optional: System Contact                        |
| snmp_location                  |                                                                         | Optional: System Location                       |
| snmp_agentadress_protocol.ipvX | udp / udp6                                                              | Optional: SNMP Protocol, X for ipv4 or ipv6     |
| snmp_agentadress_adress.ipvX   | {{ ansible_default_ipv4.address }} / {{ ansible_default_ipv6.address }} | Optional: SNMP bind address, X for ipv4 or ipv6 |
| snmp_agentadress_port.ipvX     | 161 / 161                                                               | Optional: SNMP port, X for ipv4 or ipv6         |

## Dependencies

None

## Example Playbook

```yml
- hosts: all
  roles:
    - ahpnils.snmp
```

## Changelog

### 1.8.0

- add snmp install via module

### 1.7.1

- add support for Windows 1809

### 1.7.0

- add osupdate support
- syntax cleaned up

### 1.6.0

- add distro support
- syntax cleaned up
- proxmox support

### 1.5

- add Windows Support

### 1.4

- add IP bind support

### 1.3

- add become support
- new role check
- support for sysContact and sysLocation

### 1.2

- add package manager for generic OS
- cleanup

### 1.1

- add ArchLinux support

### 1.0

- Initial release

## Authors

- [Simon Bärlocher](https://sbaerlocher.ch)
- [Nils Ratusznik](https://anotherhomepage.org)

## License

This project is under the MIT License. See the [LICENSE](https://github.com/ahpnils/ansible.snmp/blob/master/LICENSE) file for the full license text.

## Copyright

(c) 2018-2025, Simon Bärlocher
(c) 2025, Nils Ratusznik
