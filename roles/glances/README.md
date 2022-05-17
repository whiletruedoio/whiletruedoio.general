<!--
reference: https://www.makeareadme.com/
reference: https://commonmark.org/
-->

# Ansible - glances

An Ansible role to install Glances and configure the Glances web server.

## Motivation

[Glances](https://nicolargo.github.io/glances/) is a nice tool to monitor your
system interactively. It also provides a web interface option, which can be
useful in small setups. Furthermore, I needed an example for the Blog article
[Ansible - Roles 2/2](blog.while-true-do.io/ansible-roles-2/).

## Description

The role installs Glances and configures the Glances web server. You can also
customize the port for the web server.

## Usage

We are really happy, that you consider using our software. In case you want to
install and run the code on your machine, please check out this section.

### Requirements

The role supports the following target Operating System:

- Fedora Linux 35+

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

    - name: "Import glances Role"
      ansible.builtin.import_role:
        name: "whiletruedoio.general.glances"
...
```

#### Advanced Example

Use the custom port 8080.

```yaml
---
- name: "Advanced Example"

  tasks:

    - name: "Import glances Role"
      ansible.builtin.import_role:
        name: "whiletruedoio.general.glances"
      vars:
        glances_web_port: "8080"
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
