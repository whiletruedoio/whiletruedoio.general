<!--
reference: https://www.makeareadme.com/
reference: https://commonmark.org/
-->

# Ansible - firewalld

An Ansible role to install and configure
[firewalld](https://firewalld.org/).

## Motivation

Firewalld is the standard firewall service daemon on most RHEL'ish systems. As
an operator, I need to ensure it is properly installed and started for most
systems.

## Description

This Ansible role installs, configures and starts firewalld. It does not take
care of firewall policies, since these will be handled with the specific
services.

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

Install and start firewalld.

```yaml
---
- name: "Simple Example"
  hosts: "all"

  tasks:

    - name: "Import firewalld Role"
      ansible.builtin.import_role:
        name: "whiletruedoio.general.firewalld"
...
```

#### Advanced Example

Also change the default zone to "public", if not already done.

```yaml
---
- name: "Advanced Example"
  hosts: "all"

  tasks:

    - name: "Import firewalld Role"
      ansible.builtin.import_role:
        name: "whiletruedoio.general.firewalld"
      vars:
        firewalld_default_zone: "public"
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
