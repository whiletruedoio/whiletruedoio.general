<!--
reference: https://www.makeareadme.com/
reference: https://commonmark.org/
-->

# Ansible - sshd

An Ansible role to install, configure and start the
[openssh](https://www.openssh.com/) server.

## Motivation

SSH is the most common way to login to a GNU/Linux/Unix/BSD machine. It should
be installed, configured and running in a proper way by default.

## Description

The Ansible role installs and configures the openssh server on a given machine
and ensures that the firewall (firewalld) is configured properly, if installed.

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

Install and start the openssh server with default settings.

```yaml
---
- name: "Simple Example"
  hosts: "all"

  tasks:

    - name: "Import sshd Role"
      ansible.builtin.import_role:
        name: "whiletruedoio.general.sshd"
...
```

#### Advanced Example

A more advanced example, that disables root login via ssh and enable the default
banner, to be shown on login.

```yaml
---
- name: "Advanced Example"
  hosts: "all"

  tasks:

    - name: "Import ssh Role"
      ansible.builtin.import_role:
        name: "whiletruedoio.general.sshd"
      vars:
        sshd_config_PermitRootLogin: "no"
        sshd_config_Banner: "/etc/ssh/sshd_config.d/banner"
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
