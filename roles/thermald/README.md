<!--
reference: https://www.makeareadme.com/
reference: https://commonmark.org/
-->

# Ansible - thermald

An Ansible role to install, configure and start the
[thermald daemon](https://github.com/intel/thermal_daemon).

## Motivation

Thermald is a tools to prevent overheating and enabled software based throttle
for Linux machines. It is mostly used for Intel based CPUs.

## Description

The Ansible role installs and configures the thermald daemon on a given machine
and ensures that it is running. It will do nothing on AMD or ARM based systems.

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
        name: "whiletruedoio.general.thermald"
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
