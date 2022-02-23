<!--
reference: https://www.makeareadme.com/
reference: https://commonmark.org/
-->

# Ansible - misc

An Ansible role to run some miscellaneous tasks.

## Motivation

Some simple tasks don't require a dedicated role, or don't fit somewhere else.
Having a place to put them is very helpful. In case something grows bigger,
it can be ported to a new location easily.

## Description

The role currently contains the below tasks:

- hostname configuration
- timezone configuration
- machine-id creation
- tool installation

## Usage

We are really happy, that you consider using our software. In case you want to
install and run the code on your machine, please check out this section.

### Requirements

Please install the needed requirements as described below:

```shell
# Install requirements
$ ansible-galaxy install -r requirements.yml
```

### Install

This Ansible role is part of the collection
[whiletruedoio.general](https://github.com/whiletruedoio/whiletruedoio.general).

You need to install the collection to install the role.

```shell
# Install collection
$ ansible-galaxy install whiletruedoio.general
```

### Documentation

You can either use all tasks of the role or only a subset of it. Below, you can
find some example playbooks.

#### Arguments

This Ansible Role can be controlled with argmunents (options and variables), as
described in the below files.

- [meta/argument_specs.yml](meta/argument_specs.yml) provides the argument
  specification
- [defaults/main.yml](defaults/main.yml) provides all defaults for the role
- [meta/main.yml](meta/main.yml) provides some meta information, like automated
  dependencies

#### Simple Example

Just run all tasks from the role.

```yaml
---
- name: "Simple Example"
  hosts: "all"

  tasks:

    - name: "Import misc Role"
      ansible.builtin.import_role:
        name: "whiletruedoio.general.misc"
...
```

#### Advanced Example

Only use the timezone tasks from the role.

```yaml
---
- name: "Advanced Example"
  hosts: "all"

  tasks:

    - name: "Import timezone tasks misc Role"
      ansible.builtin.import_role:
        name: "whiletruedoio.general.misc"
        tasks_from: "timezone"
...
```

Only use the hostname tasks from the role and specify your own hostname.

```yaml
---
- name: "Advanced Example"
  hosts: "all"

  tasks:

    - name: "Import hostname tasks misc Role"
      ansible.builtin.import_role:
        name: "whiletruedoio.general.misc"
        tasks_from: "hostname"
      vars:
        misc_config_hostname: "host01"
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
