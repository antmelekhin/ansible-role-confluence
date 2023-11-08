Confluence
==========

An Ansible role for install, configure and update [Confluence](https://www.atlassian.com/ru/software/confluence).

Requirements
------------

- Supported version of Ansible: 2.9 and highter.
- Supported platforms:
  - Debian
    - 10
    - 11
  - RHEL
    - 7
    - 8
  - Ubuntu
    - 18.04
    - 20.04

Role Variables
--------------

- `confluence_version` The specific version of Confluence to download (default: `8.5.3`).
- `confluence_archive_name` Confluence archive name (default: `atlassian-confluence-8.5.3.tar.gz`).
- `confluence_download_url` URL to download an archive with Confluence (default: `https://www.atlassian.com/software/confluence/downloads/binary`).
- `confluence_username` and `confluence_group` Unix username and group (default: `confluence`).
- `confluence_root_path` Path to Confluence installation directory (default: `/opt/atlassian/confluence`).
- `confluence_home_path` Path to Confluence home directory (default: `/var/atlassian/application-data/confluence`).
- `confluence_jvm_minimum_memory` and `confluence_jvm_maximum_memory` The minimum and maximum size of the heap (default: `1024m` and `2048m`).
- DB connection settings, read [documentation](https://confluence.atlassian.com/conf713/configuring-a-datasource-connection-1077914464.html) before enable.
  - `confluence_db_configuration` DB connection configuration (default: `false`).
  - `confluence_db_address` IP address or DNS name of DB server.
  - `confluence_db_port` DB port.
  - `confluence_db_name` DB name.
  - `confluence_db_username` DB username.
  - `confluence_db_password` DB password.
- `confluence_tomcat_connector_proxyname` Fqdn server name. If you don't use a reverse proxy, then you'll need to leave this variable without value.
- `confluence_tomcat_connector_scheme` Connection scheme.

  Available values:
  - `http` (default)
  - `https`

    **Attention** If you use `https` value, you'll need to install SSL sertificate on server with reverse proxy.

- `confluence_tomcat_connector_proxyport` Server port (default: `80` or `443`).
  - `80` sets automatically if value in `confluence_tomcat_connector_scheme` is `http`.
  - `443` sets automatically if value in `confluence_tomcat_connector_scheme` is `https`.

Dependencies
------------

This role doesn't install `java`, reverse proxy (`apache` or `nginx`) and DB management system. You'll need to install packages before using.

Example Playbook
----------------

- Install `Confluence`, `java` and configure connection to DB over Confluence web interface:

  - Install dependencies:

    ```bash
    ansible-galaxy install -r requirements.yml
    ```

  - Run playbook:

    ```yaml
    ---

    - name: Setup Confluence
      hosts: confluence

      roles:
        - role: geerlingguy.java
        - role: antmelekhin.confluence
    ```

License
-------

MIT

Author Information
------------------

Melekhin Anton.
