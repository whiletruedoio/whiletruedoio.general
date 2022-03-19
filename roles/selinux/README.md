<!--
reference: https://www.makeareadme.com/
reference: https://commonmark.org/
-->

# Ansible - selinux

An Ansible role to install and configure [SELinux](https://selinuxproject.org/).

## Motivation

SELinux is used on all RHEL'ish derivates to add another layer of security. An
operator needs to ensure that is installed and configured the desired way.

## Description

The role installs and configures SELinux on RHEL'ish GNU/Linux systems like
Fedora, CentOS, AlmaLinux or Red Hat Enterprise Linux. You can also choose the
policy and state of SELinux.

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

A simple example, using the defaults (packages installed and SELinux enforcing).

```yaml
---
- name: "Simple Example"
  hosts: "all"

  tasks:

    - name: "Import selinux Role"
      ansible.builtin.import_role:
        name: "whiletruedoio.general.selinux"
...
```

#### Advanced Example

A more advanced example, that sets the policy to permissive.

```yaml
---
- name: "Advanced Example"
  hosts: "all"

  tasks:

    - name: "Import selinux Role"
      ansible.builtin.import_role:
        name: "whiletruedoio.general.selinux"
      vars:
        selinux_config_policy: "permissive"
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
