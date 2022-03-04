<!--
reference: https://www.makeareadme.com/
reference: https://commonmark.org/
-->

# Ansible - dnf

An Ansible Role to install and configure the
[DNF package manager](https://DNF.readthedocs.io/en/latest/).

## Motivation

DNF is the standard Package Manager for all RHEL'ish GNU/Linux derivates, like
CentOS, Fedora or Red Hat Enterprise Linux. Configuring it properly is mandatory
for most operators.

## Description

The role install DNF and additional plugins to configure parallel downloads or
chosing of the fastest mirror.

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

Just a simple example, using the defaults from the role.

```yaml
---
- name: "Simple Example"
  hosts: "all"

  tasks:

    - name: "Import dnf Role"
      ansible.builtin.import_role:
        name: "whiletruedoio.general.dnf"
...
```

#### Advanced Example

You can also raise/lower or raise the parallel downloads and change the dnf
configuration as demonstrated below.

```yaml
---
- name: "Advanced Example"
  hosts: "all"

  tasks:

    - name: "Import dnf Role"
      ansible.builtin.import_role:
        name: "whiletruedoio.general.dnf"
      vars:
        dnf_config_parallel_downloads: 5
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
