Confluence
==========

An Ansible role to install, configure and update [Confluence](https://www.atlassian.com/ru/software/confluence).

Upgrade to 2.x
--------------

In version 2.0.0, the `confluence_root_path` variable was renamed to `confluence_install_path`.

Requirements
------------

- Supported version of Ansible: 2.12 and higher. Systems with Python versions below than 3.7 are not compatible with ansible-core 2.17 (see [ansible/ansible#83357](https://github.com/ansible/ansible/issues/83357#issuecomment-2150254754)).
- Supported platforms:
  - Debian
    - 10
    - 11
    - 12
  - RHEL
    - 7
    - 8
    - 9
  - Ubuntu
    - 18.04
    - 20.04
    - 22.04

Role Variables
--------------

All variables that can be overridden are stored in the [defaults/main.yml](https://github.com/antmelekhin/ansible-role-confluence/blob/main/defaults/main.yml) file.
Please refer to the [meta/argument_specs.yml](https://github.com/antmelekhin/ansible-role-confluence/blob/main/meta/argument_specs.yml) file for a description of the available variables.
Similarly, descriptions and defaults for preset variables can be found in the [vars/main.yml](https://github.com/antmelekhin/ansible-role-confluence/blob/main/vars/main.yml) file.

Dependencies
------------

This role doesn't install a `Java` package, a reverse proxy (`Apache` or `Nginx`), or a database management system. You will need to install these packages before using the role.

Example Playbook
----------------

Install Confluence, Java package, and configure a connection to the database through the Confluence web interface:

Install dependencies:

```bash
ansible-galaxy install -r requirements.yml
```

Run playbook:

```yaml
---
- name: Setup Confluence
  hosts: confluence

  roles:
    - role: antmelekhin.java
    - role: antmelekhin.confluence
```

License
-------

MIT

Author Information
------------------

Melekhin Anton.
