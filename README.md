Aptsource
=========

[![Build Status](https://travis-ci.org/dochang/ansible-role-aptsource.svg?branch=master)](https://travis-ci.org/dochang/ansible-role-aptsource)
[![Ansible Galaxy](https://img.shields.io/badge/galaxy-dochang.aptsource-blue.svg)](https://galaxy.ansible.com/dochang/aptsource/)

An ansible role to configure Debian APT sources.

Requirements
------------

None

Role Variables
--------------

  - `aptsource_uri` (default: `http://httpredir.debian.org/debian`)
  - `aptsource_security_uri` (default: `http://security.debian.org/`)
  - `aptsource_stable_updates_enabled` (default: `yes`)
  - `aptsource_stable_updates_uri` (default: `http://httpredir.debian.org/debian`)
  - `aptsource_backports_enabled`: (default: `no`)
  - `aptsource_backports_uri` (default: `http://httpredir.debian.org/debian`)
  - `aptsource_suite` (default: `{{ (ansible_distribution_release != "NA") | ternary(ansible_distribution_release, "sid") }}`)
  - `aptsource_components` (default: `[ main, contrib, non-free ]`)

Dependencies
------------

None

Example Playbook
----------------

    - hosts: servers
      roles:
        - role: dochang.aptsource
          aptsource_uri: http://httpredir.debian.org/debian
          aptsource_backports_enabled: yes
          aptsource_backports_enabled: http://httpredir.debian.org/debian
          aptsource_suite: sid
          aptsource_components:
            - main
            - contrib
            - non-free

License
-------

[MIT](https://dochang.mit-license.org/)

Author Information
------------------

Desmond O. Chang <dochang@gmail.com>
