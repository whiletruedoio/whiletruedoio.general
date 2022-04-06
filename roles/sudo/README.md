<!--
reference: https://www.makeareadme.com/
reference: https://commonmark.org/
-->

# Ansible - sudo

An Ansible role to install and configure [sudo](https://www.sudo.ws/).

## Motivation

Sudo (su “do”) allows a system administrator to delegate authority to give
certain users (or groups of users) the ability to run some (or all) commands as
root or another user while providing an audit trail of the commands and their
arguments. Sudo is an essential tool for most GNU/Linux machines and configuring
the same is very common.

## Description

The Ansible role installs and configures sudo.

## Usage

We are really happy, that you consider using our software. In case you want to
install and run the code on your machine, please check out this section.

### Requirements

None, expect a RHEL derivate/family system as the managed node.

### Install

This Ansible role is part of the collection
[whiletruedoio.general](https://github.com/whiletruedoio/whiletruedoio.general).

You need to install the collection to install the role.

```shell
# Install collection
$ ansible-galaxy install whiletruedoio.general
```

### Documentation

Below you can find some simple examples and specs for the role.

#### Arguments

This Ansible Role can be controlled with argmunents (options and variables), as
described in the below files.

- [meta/argument_specs.yml](meta/argument_specs.yml) provides the argument
  specification
- [defaults/main.yml](defaults/main.yml) provides all defaults for the role
- [meta/main.yml](meta/main.yml) provides some meta information, like automated
  dependencies

#### Simple Example

Ensure sudo is installed and the default configuration is applied.

```yaml
---
- name: "Simple Example"
  hosts: "all"

  tasks:

    - name: "Import sudo Role"
      ansible.builtin.import_role:
        name: "whiletruedoio.general.sudo"
...
```

#### Advanced Example

Permit the wheel group to use sudo without providing the password.

```yaml
---
- name: "Advanced Example"
  hosts: "all"

  tasks:

    - name: "Import sudo Role"
      ansible.builtin.import_role:
        name: "whiletruedoio.general.sudo"
      vars:
        sudo_conf_wheel_group:
          enabled: true
          tag: "NOPASSWD"
...
```

Permit the user bob and alice and the webadmin group to run specific commands
via sudo.

```yaml
---
- name: "Advanced Example"
  hosts: "all"

  tasks:

    - name: "Import sudo Role"
      ansible.builtin.import_role:
        name: "whiletruedoio.general.sudo"
      vars:
        sudo_conf_sudoers:
          - name: "bob"
            type: "user"
            host: "ALL"
            runas: "ALL"
            cmnd: "dnf update"
          - name: "alice"
            type: "user"
            host: "ALL"
            runas: "ALL"
            cmnd: "systemctl reboot"
          - name: "webadmin"
            type: "group"
            host: "ALL"
            runas: "ALL"
            cmnd: "systemctl restart httpd"
...
```

## Contact

Please feel free to reach out to us and the community. We also recommend to read
and understand the
[Code of Conduct](https://github.com/whiletruedoio/.github/blob/main/docs/CODE_OF_CONDUCT.md)
beforehand.

- Site: <https://while-true-do.io>
- Blog: <https://blog.while-true-do.io>
- Code: <https://github.com/whiletruedoio>
- Chat: [libera.chat #whiletruedoio](https://web.libera.chat/gamja/#whiletruedo)
- Mail: [hello@while-true-do.io](mailto:hello@while-true-do.io)
