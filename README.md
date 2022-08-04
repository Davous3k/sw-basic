Ansible role for deploy basic packages and services. You can add custom services or packages via variables bellow.

This role is developed with Ansible 2.9.6 and tested on Ubuntu 20.04 LTS.

## Role Variables

| Variable | Required | Default | Comments |
| -------- | -------- | ------- | -------- |
| `additional_pkgs` | No | `{}` | Add aditional packages while using this role |
| `additional_services` | No | `{}` | Add aditional services while using this role |
| `sshd_username` | No | `root` | Define SSH user. MUST BE created on target system.                   |
| `sshd_key_file_name` | No | `key.pub` | Define SSH public key file name in this role. (files/key.pub) |
| `sshd_service_state` | No | `started` | Set SSH service state, started, enabled or disabled. |
| `sshd_service_enabled` | No | `yes` | Enable SSH service on system boot. |
| `additional_services_state` | No | `started` | Set additional service state, started, enabled or disabled. |
| `sshd_service_enabled` | No | `yes` | Enable additional service on system boot. |

## Requirements

Ansible.posix collection

To install it, use the following command:

```yaml
ansible-galaxy collection install ansible.posix
```

## Install basic packages and services with default settings
```yaml
  roles:
     - sw-basic
```

## Install basic packages and services with some custom variables
```yaml
  roles:
     - sw-basic
  vars:
     - sshd_key_file_name:
        - newfilename.pub
```

