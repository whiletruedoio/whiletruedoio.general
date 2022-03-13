<!--
reference: https://www.makeareadme.com/
reference: https://commonmark.org/
-->

[![Cirrus CI - Base Branch Build Status](https://img.shields.io/cirrus/github/whiletruedoio/whiletruedoio.general?logo=Cirrus-ci)](https://cirrus-ci.com/github/whiletruedoio/whiletruedoio.general)
[![GitHub release (latest SemVer)](https://img.shields.io/github/v/release/whiletruedoio/whiletruedoio.general?logo=GitHub&label=Release&sort=semver)](https://github.com/whiletruedoio/whiletruedoio.general/releases)
[![GitHub issues](https://img.shields.io/github/issues/whiletruedoio/whiletruedoio.general)](https://github.com/whiletruedoio/whiletruedoio.general/issues)
[![GitHub pull requests](https://img.shields.io/github/issues-pr/whiletruedoio/whiletruedoio.general)](https://github.com/whiletruedoio/whiletruedoio.general/pulls)
[![GitHub license](https://img.shields.io/github/license/whiletruedoio/whiletruedoio.general)](https://github.com/whiletruedoio/whiletruedoio.general/blob/main/LICENSE)

# Ansible - whiletruedoio.general

Ansible collection for general purpose plugins, roles and playbooks.

## Motivation

At [while-true-do.io](https://while-true-do.io), we faced the situation, that
we wanted to automate our setups. In the past, this was done with many different
repositories (one per role / setup plugin). With Ansible collections, it is
possible to bundle these properly and in a convenient way.

## Description

This collection takes care of general purpose plugins, roles and playbooks as
described below. A role is considered "general purpose" as long as it does not
fit properly in another collection.

### Plugins

None.

### Roles

All of the roles are providing argument specifications and additional (optional)
checks to improve handling and usability. Some roles also improve security by
applying common security patterns from [OpenSCAP](https://www.open-scap.org/).
The following roles are bundled with this collection.

- [Avahi](roles/avahi/README.md)
- [Bash](roles/bash/README.md)
- [Chrony](roles/chrony/README.md)
- [Cockpit](roles/cockpit/README.md)
- [dnf](roles/dnf/README.md)
- [firewalld](roles/firewalld/README.md)
- [k3s](roles/k3s/README.md)
- [misc](roles/misc/README.md)
- [Podman](roles/podman/README.md)
- [SELinux](roles/selinux/README.md)
- [sshd](roles/sshd/README.md)
- [thermald](roles/thermald/README.md)
- [user](roles/user/README.md)

### Playbooks

The following playbooks are bundled with this collection and provide examples
for role usage or templates for further improvements.

- [minimal server](playbooks/minimal_server.yml)

## Usage

We are really happy, that you consider using our software. In case you want to
install and run the code on your machine, please check out this section.

### Requirements

The provided playbooks, plugins and roles require Ansible-Core 2.12 on the
**control node**.

The provided playbooks, plugins and roles support the following Operating System
on the **target nodes**:

- Fedora Linux 35+
- CentOS Stream 8+
- AlmaLinux 8+
- RockyLinux 8+

### Install

Installing an Ansible collection can be done in multiple ways.

#### Via Ansible Galaxy

This is the most common way for users and will install the collection in the
proper directories. It will also install the required dependency colections.

```sh
# Install
$ ansible-galaxy collection install whiletruedoio.general

# Update
$ ansible-galaxy collection install whiletruedoio.general --upgrade

# Remove
$ ansible-galaxy collection install whiletruedoio.general
```

#### Via Git Repository

For development purposes, you can also clone the repository and copy it to your
desired location. Be aware, that you need to install dependencies on your own.

```sh
# Clone
$ git clone https://github.com/whiletruedoio/whiletruedoio.general.git

# Update
$ cd /path/to/repository
$ git pull
```

### Documentation

<!-- TODO: Documentation

This section describes how to use this collection and where to find additional
documentation.

First steps after the installation?
Important things the user/admin should know?
Could you provide examples to use the code?
Were to find additional documentation?

Optional: Use and link docs/*.md files
-->

## Contribute

Thank you so much for considering to contribute! We are happy, when someone is
joining the hard work.

### Issues

Issues and Pull Requests are handled on a regular basis. Please be aware, that
we may reach out to you, ask you to provide additional resources or want to
discuss the issue a little, before planning it.

- [Bugs and Feature Requests](https://github.com/whiletruedoio/whiletrueodio.general/issues)
- [Pull Requests](https://github.com/whiletruedoio/whiletrueodio.general/pulls)

### Develop

Providing code to this repository is pretty straight forward. Open an issue,
so we can discuss the bug/feature and start working on it afterwards. You just
need to open the pull request afterwards and that's it.

It is also strongly recommended to read the
[Contribution Guideline](https://github.com/whiletruedoio/.github/blob/main/docs/CONTRIBUTING.md)
beforehand.

### Changelog

We are maintaining a [changelog](CHANGELOG.md) for repositories. Normally, the
developers will update the changelog, according to
[keepachangelog.com](https://keepachangelog.com/).

### Test

To ensure a high quality and functionality, we want to carefully test our
software. The provided code is automatically tested as described in the
[.cirrus.yml](.cirrus.yml).

Each plugin, role and playbook provides tests, located in
[tests/](./tests/). The below example demonstrates, how you can use them.

```shell
# Run linting test in Docker/Podman
$ ansible-test sanity --lint --docker

# Run only yamllint in Docker/Podman
$ ansible-test sanity --test yamllint --docker

# Run integration tests in Docker/Podman
$ ansible-test integration --docker fedora34

# Run a specific integration test in Docker/Podman
$ ansible-test integration --docker fedora34 role_myrole
```

Please also check the
[documentation for ansible-test](https://docs.ansible.com/ansible/latest/dev_guide/developing_collections_testing.html#testing-collections).

## License

Except otherwise noted, all work is [licensed](LICENSE) under a
[BSD-3-Clause License](https://opensource.org/licenses/BSD-3-Clause).

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
