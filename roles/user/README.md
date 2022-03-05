<!--
reference: https://www.makeareadme.com/
reference: https://commonmark.org/
-->

# Ansible - user

An Ansible role to create and update a list of users.

## Motivation

Creating, updating and removing users on a couple of machines can be done with
central infrastructure like LDAP. For a small amount machines, this may be
impossible or not worth the effort. Additionally, one may need a couple of
local users for rescue purposes or technical usage.

## Description

This role aims to make the user creation easy and maintainable for a small
amount of machines, where local users are needed. You can:

- create, update, remove users
- update authorized keys for users
- assign users to one or more groups

## Usage

We are really happy, that you consider using our software. In case you want to
install and run the code on your machine, please check out this section.

### Requirements

None.

### Install

This Ansible role is part of the collection
[while_true_do.general](https://code.while-true-do.io/ansible/while_true_do.general).

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

#### Creating a password hash

If you want to use this role and provide passwords, you have to create valid
password hashes beforehand. This can be done with one of the following commands:

With Ansible:

```shell
$ ansible all -i localhost, -m debug -a "msg={{ 'mypassword' | password_hash('sha512', 'mysecretsalt') }}"
```

With mkpasswd:

```shell
$ mkpasswd --method=sha-512
Password:
$6$2Y0zoyxnp5NMdF0T$4jweZk15WtT1Y.CYswo0GLs.Mb9ah2xWEWDFVQEIQEtZggbIo7hY0PX5rbdJ7CNseuc69D203W6WbbPRMtEln0
```

With Python:

```shell
$ python -c "from passlib.hash import sha512_crypt; import getpass; print(sha512_crypt.using(rounds=5000).hash(getpass.getpass()))"
```

#### Simple Example

Just the create the user "alice" with the given defaults and a password.

```yaml
---
- name: "Simple Example"
  hosts: "all"

  tasks:

    - name: "Import user Role"
      ansible.builtin.import_role:
        name: "whiletruedoio.general.user"
      vars:
        user_users:
          - name: "alice"
            password: "$6$54ccYz.J0kxZwtZh$nL28pAsiNNznwMQ3uYbu4zSuYFmHDcuLRjGPTH/POKTbTpiL8hiYXqgz0ebeMPryoLLYd1yl7cUvGuuBUxpZO."
...
```

#### Advanced Example

Create the user "alice" and "bob" and add both to the wheel group. "Bob" also
has a public key, that should be copied to the system.

```yaml
---
- name: "Advanced Example"
  hosts: "all"

  tasks:

    - name: "Import user Role"
      ansible.builtin.import_role:
        name: "whiletruedoio.general.user"
      vars:
        user_users:
          - name: "alice"
            password: "$6$8wV5pjkY7jJn147A$JmIsU0FO6wrXga3YQ1HOpb6SjjE4S.Ik7Tp7HI5fjtFDSeuB..i2yBHz6Pl7brkCkx5TTaCMXjvi7qu1IHNID/"
            groups: "wheel"
          - name: "bob"
            password: "$6$54ccYz.J0kxZwtZh$nL28pAsiNNznwMQ3uYbu4zSuYFmHDcuLRjGPTH/POKTbTpiL8hiYXqgz0ebeMPryoLLYd1yl7cUvGuuBUxpZO."
            groups: "wheel"
            auth_keys:
              - key: "ssh-rsa AAAAB3NzaC1yc....ZV8gs3Fc= bob@example.com"
...
```

Ensure "bob" and "alice" are created (as before), but "chuck" is removed.

```yaml
---
- name: "Advanced Example"
  hosts: "all"

  tasks:

    - name: "Import user Role"
      ansible.builtin.import_role:
        name: "whiletruedoio.general.user"
      vars:
        user_users:
          - name: "alice"
            password: "$6$8wV5pjkY7jJn147A$JmIsU0FO6wrXga3YQ1HOpb6SjjE4S.Ik7Tp7HI5fjtFDSeuB..i2yBHz6Pl7brkCkx5TTaCMXjvi7qu1IHNID/"
          - name: "bob"
            password: "$6$54ccYz.J0kxZwtZh$nL28pAsiNNznwMQ3uYbu4zSuYFmHDcuLRjGPTH/POKTbTpiL8hiYXqgz0ebeMPryoLLYd1yl7cUvGuuBUxpZO."
            auth_keys:
              - key: "ssh-rsa AAAAB3NzaC1yc....ZV8gs3Fc= bob@example.com"
          - name: "chuck"
            state: "absent"
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
