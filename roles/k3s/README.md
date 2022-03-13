<!--
reference: https://www.makeareadme.com/
reference: https://commonmark.org/
-->

# Ansible - k3s

An Ansible role to install and configure [k3s](https://k3s.io/).

## Motivation

Having a small kubernetes machine or cluster on hand can be useful for
development, edge computing and home clouds. k3s is very well known and sees
constant support and development. Is also includes some tools, that you might
need like kube-metrics, a local storage driver and an ingress-controller.

## Description

The role installs and configures k3s, including dependencies and fetching the
connection data.

For now, the following setups are supported

- single k3s host

## Usage

We are really happy, that you consider using our software. In case you want to
install and run the code on your machine, please check out this section.

### Requirements

The role supports the following target Operating System:

- Fedora Linux 35+
- CentOS Stream 8+
- AlmaLinux 8+
- RockyLinux 8+

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

Use the role defaults.

```yaml
---
- name: "Simple Example"
  hosts: "all"

  tasks:

    - name: "Import k3s Role"
      ansible.builtin.import_role:
        name: "whiletruedoio.general.k3s"
...
```

#### Advanced Example

Providing a custom token.

```yaml
---
- name: "Advanced Example"
  hosts: "all"

  tasks:

    - name: "Import k3s Role"
      ansible.builtin.import_role:
        name: "whiletruedoio.general.k3s"
      vars:
        k3s_token: "myCustomToken"
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
