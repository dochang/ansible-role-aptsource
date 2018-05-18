Aptsource
=========

[![Build Status](https://travis-ci.org/dochang/ansible-role-aptsource.svg?branch=master)](https://travis-ci.org/dochang/ansible-role-aptsource)
[![Ansible Galaxy](https://img.shields.io/badge/galaxy-dochang.aptsource-blue.svg)](https://galaxy.ansible.com/dochang/aptsource/)
[![Average time to resolve an issue](http://isitmaintained.com/badge/resolution/dochang/ansible-role-aptsource.svg)](http://isitmaintained.com/project/dochang/ansible-role-aptsource "Average time to resolve an issue")
[![Percentage of issues still open](http://isitmaintained.com/badge/open/dochang/ansible-role-aptsource.svg)](http://isitmaintained.com/project/dochang/ansible-role-aptsource "Percentage of issues still open")

An ansible role to configure Debian APT sources.

Requirements
------------

None

Role Variables
--------------

  - `aptsource_sources_enabled` (default: `no`)
  - `aptsource_debian_uri` (default: `http://deb.debian.org/debian`)
  - `aptsource_debian_security_uri` (default: `http://deb.debian.org/debian-security`)
  - `aptsource_debian_stable_updates_enabled` (default: `yes`)
  - `aptsource_debian_stable_updates_uri` (default: `{{ aptsource_debian_uri }}`)
  - `aptsource_debian_backports_enabled` (default: `no`)
  - `aptsource_debian_backports_uri` (default: `{{ aptsource_debian_uri }}`)
  - `aptsource_debian_debug_enabled` (default: `no`)
  - `aptsource_debian_debug_uri` (default: `http://deb.debian.org/debian-debug`)
  - `aptsource_debian_ports_enabled` (default: `no`)
  - `aptsource_debian_ports_uri` (default: `http://deb.debian.org/debian-ports`)
  - `aptsource_debian_ports_suite` (default: `{{ aptsource_debian_suite }}`)
  - `aptsource_debian_suite` (default: `{{ ansible_lsb.codename }}`)
  - `aptsource_debian_components` (default: `[ main, contrib, non-free ]`)

Dependencies
------------

None

Example Playbook
----------------

    - hosts: servers
      roles:
        - role: dochang.aptsource
          aptsource_debian_uri: http://deb.debian.org/debian
          aptsource_debian_backports_enabled: yes
          aptsource_debian_backports_uri: '{{ aptsource_debian_uri }}'
          aptsource_debian_suite: sid
          aptsource_debian_components:
            - main
            - contrib
            - non-free

License
-------

[MIT](https://dochang.mit-license.org/)

Author Information
------------------

Desmond O. Chang <dochang@gmail.com>
