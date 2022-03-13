<!--
reference: https://www.makeareadme.com/
reference: https://commonmark.org/
-->

# Ansible - podman

<!-- Short Description -->

## Motivation

<!-- TODO: Motivation

This section describes the motivation to create the Ansible Role and why it is
needed.
-->

## Description

<!-- TODO: Description

This section describes the role. Which software or configuration is automated
and how does this role help?
-->

## Usage

We are really happy, that you consider using our software. In case you want to
install and run the code on your machine, please check out this section.

### Requirements

<!-- TODO: Requirements

This section describes what one needs to run the code in production.

Please mention all dependencies on the control node and/or managed node. Please
also check, if a special Ansible Version is needed on the control node.

Lastly, if your role depends on another role or collection, please maintain the
requirements.yml and provide an installation example.

```shell
# Install required roles and collections

$ ansible-galaxy install -r requirements.yml
```
-->

### Install

<!-- TODO: Install

This section describes how to install the Ansible Role. Please link the proper
collection, if the role is bundled in one.
-->

### Documentation

Below you can find some simple examples and specs for the role.

<!-- TODO: Documentation

This section describes how to use the Ansible Role. Please provide at least an
introduction sentence, an example and link to special files like meta/main.yml,
meta/argument_specs.yml or defaults/main.yml.
-->

#### Arguments

This Ansible Role can be controlled with argmunents (options and variables), as
described in the below files.

- [meta/argument_specs.yml](meta/argument_specs.yml) provides the argument
  specification
- [defaults/main.yml](defaults/main.yml) provides all defaults for the role
- [meta/main.yml](meta/main.yml) provides some meta information, like automated
  dependencies

#### Simple Example

<!-- Description for the simple example. -->

```yaml
---
- name: "Simple Example"
  hosts: "all"

  tasks:

    - name: "Import podman Role"
      ansible.builtin.import_role:
        name: "podman"
...
```

#### Advanced Example

<!-- Description for the advanced example. -->

```yaml
---
- name: "Advanced Example"
  hosts: "all"

  tasks:

    - name: "Import podman Role"
      ansible.builtin.import_role:
        name: "podman"
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
