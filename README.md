# [Ansible role bind](#ansible-role-bind)

Setup ISC BIND as an authoritative DNS server for one or more domains (primary and/or secondary).

|GitHub|Issues|Pull Requests|Version|Downloads|
|------|------|-------------|-------|---------|
|[![github](https://github.com/buluma/ansible-role-bind/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-bind/actions/workflows/molecule.yml)|[![Issues](https://img.shields.io/github/issues/buluma/ansible-role-bind.svg)](https://github.com/buluma/ansible-role-bind/issues/)|[![PullRequests](https://img.shields.io/github/issues-pr-closed-raw/buluma/ansible-role-bind.svg)](https://github.com/buluma/ansible-role-bind/pulls/)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-bind.svg)](https://github.com/buluma/ansible-role-bind/releases/)|[![Ansible Role](https://img.shields.io/ansible/role/d/buluma/bind)](https://galaxy.ansible.com/ui/standalone/roles/buluma/bind/documentation)|

## [Example Playbook](#example-playbook)

This example is taken from [`molecule/default/converge.yml`](https://github.com/buluma/ansible-role-bind/blob/master/molecule/default/converge.yml) and is tested on each push, pull request and release.

```yaml
---
- hosts: all
  name: Converge
  tasks:
    - ansible.builtin.include_role:
        name: buluma.bind
      name: Include buluma.bind
```

The machine needs to be prepared. In CI this is done using [`molecule/default/prepare.yml`](https://github.com/buluma/ansible-role-bind/blob/master/molecule/default/prepare.yml):

```yaml
---
- become: true
  gather_facts: true
  hosts: all
  name: Prepare
  roles:
    - role: buluma.bootstrap
```

Also see a [full explanation and example](https://buluma.github.io/how-to-use-these-roles.html) on how to use these roles.

## [Role Variables](#role-variables)

The default values for the variables are set in [`defaults/main.yml`](https://github.com/buluma/ansible-role-bind/blob/master/defaults/main.yml):

```yaml
---
bind_acls: []
bind_allow_query:
  - localhost
bind_allow_recursion:
  - any
bind_dns64: false
bind_dns64_clients:
  - any
bind_dns_keys: []
bind_dnssec_enable: true
bind_dnssec_validation: true
bind_extra_include_files: []
bind_forward_only: false
bind_forwarders: []
bind_key_mapping: {}
bind_listen_ipv4:
  - 127.0.0.1
bind_listen_ipv4_port:
  - 53
bind_listen_ipv6:
  - ::1
bind_listen_ipv6_port:
  - 53
bind_log: data/named.run
bind_python_version: "{{ bind_default_python_version }}"
bind_recursion: false
bind_rrset_order: random
bind_statistics_allow:
  - 127.0.0.1
bind_statistics_channels: false
bind_statistics_host: "127.0.0.1"
bind_statistics_port: 8053
bind_zone_file_mode: "0640"
bind_zone_minimum_ttl: 1D
bind_zone_time_to_expire: 1W
bind_zone_time_to_refresh: 1D
bind_zone_time_to_retry: 1H
bind_zone_ttl: 1W
bind_zones: []
```

## [Requirements](#requirements)

- pip packages listed in [requirements.txt](https://github.com/buluma/ansible-role-bind/blob/master/requirements.txt).

## [State of used roles](#state-of-used-roles)

The following roles are used to prepare a system. You can prepare your system in another way.

| Requirement | GitHub |
|-------------|--------|
|[buluma.bootstrap](https://galaxy.ansible.com/buluma/bootstrap)|[![Build Status GitHub](https://github.com/buluma/ansible-role-bootstrap/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-bootstrap/actions)|
|[buluma.sysctl](https://galaxy.ansible.com/buluma/sysctl)|[![Build Status GitHub](https://github.com/buluma/ansible-role-sysctl/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-sysctl/actions)|

## [Context](#context)

This role is part of many compatible roles. Have a look at [the documentation of these roles](https://buluma.github.io/) for further information.

Here is an overview of related roles:

![dependencies](https://raw.githubusercontent.com/buluma/ansible-role-bind/png/requirements.png "Dependencies")

## [Compatibility](#compatibility)

This role has been tested on these [container images](https://hub.docker.com/u/robertdebock):

|container|tags|
|---------|----|
|[Debian](https://hub.docker.com/r/robertdebock/debian)|all|
|[EL](https://hub.docker.com/r/robertdebock/enterpriselinux)|all|
|[Ubuntu](https://hub.docker.com/r/robertdebock/ubuntu)|all|

The minimum version of Ansible required is 2.12, tests have been done on:

- The previous version.
- The current version.
- The development version.

If you find issues, please register them on [GitHub](https://github.com/buluma/ansible-role-bind/issues).

## [License](#license)

[Apache-2.0](https://github.com/buluma/ansible-role-bind/blob/master/LICENSE).

## [Author Information](#author-information)

[buluma](https://buluma.github.io/)

### Get Help
- Report issues: https://github.com/buluma/ansible-role-bind/issues/new
- See docs: https://docs.ansible.com/collection/gallery/ansible-role-bind
