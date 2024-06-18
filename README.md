Confluence
==========

An Ansible role to install, configure and update [Confluence](https://www.atlassian.com/ru/software/confluence).

Requirements
------------

- Supported version of Ansible: 2.9 and highter.
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

- `confluence_version` The version of Confluence to download (default: `8.5.11`).
- `confluence_archive_name` Confluence archive name (default: `atlassian-confluence-8.5.11.tar.gz`).
- `confluence_download_url` URL to download the Confluence archive (default: `https://www.atlassian.com/software/confluence/downloads/binary`).
- `confluence_download_path` Local path to download and extract the archive (default: `/tmp`).
- `confluence_user` and `confluence_group` System user and group that will be created (default: `confluence`).
- `confluence_root_path` The Confluence installation directory (default: `/opt/atlassian/confluence`).
- `confluence_home_path` The Confluence home directory (default: `/var/atlassian/application-data/confluence`).
- `confluence_jvm_minimum_memory` and `confluence_jvm_maximum_memory` The minimum and maximum size of the heap (default: `1024m` and `2048m`).
- `confluence_db_configuration` DB connection settings, read [documentation](https://confluence.atlassian.com/conf85/configuring-a-datasource-connection-1283361007.html) before enable (default: `false`).
- `confluence_db_host` Hostname or IP address of your database server.
- `confluence_db_port` TCP port number for your database server.
- `confluence_db_name` DB name.
- `confluence_db_username` and `confluence_db_password` Database username and password to be passed to the JDBC driver.
- `confluence_tomcat_connector_proxyname` Fqdn server name. If you don't use a reverse proxy, then you'll need to leave this variable without value.
- `confluence_tomcat_connector_scheme` Connection scheme. Available values: `http` (default), `https`.

    **Attention** If you use `https` value, you'll need to install SSL sertificate on server with reverse proxy.

- `confluence_tomcat_connector_proxyport` Server port (default: `80` or `443`).
  - `80` sets automatically if value in `confluence_tomcat_connector_scheme` is `http`.
  - `443` sets automatically if value in `confluence_tomcat_connector_scheme` is `https`.

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
