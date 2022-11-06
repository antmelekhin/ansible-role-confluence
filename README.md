Confluence
==========

Ansible роль для установки, настройки и обновления [Confluence](https://www.atlassian.com/ru/software/confluence).

Требования
----------

- Поддерживаемая версия Ansible: 2.9 и выше.
- `gnu-tar` при использовании Mac в качестве управляющего хоста (`brew install gnu-tar`).
- Список поддерживаемых платформ описан в файле метаданных роли.

Используемые переменные
-----------------------

- `confluence_version` Версия Confluence для установки (default: `7.13.1`).
- `confluence_download_url` Ссылка на скачивание архива с приложением.
- `confluence_username` Unix имя пользователя (default: `confluence`).
- `confluence_group` Unix группа пользователя (default: `confluence`).
- `confluence_root_path` Каталог, в который будет распакован архив и установлено приложение (default: `/opt/atlassian/confluence`).
- `confluence_home_path` Домашний каталог Confluence (default: `/var/atlassian/application-data/confluence`).
- `confluence_jvm_minimum_memory` Минимальный объем памяти, используемый JVM (default: `1024m`).
- `confluence_jvm_maximum_memory` Максимальный объем памяти, используемый JVM (default: `1024m`).
- Настройки подключения к базе данных, прежде чем включать ознакомтесь с [документацией](https://confluence.atlassian.com/conf713/configuring-a-datasource-connection-1077914464.html).
  - `confluence_db_configuration` Настройка подключения к БД (default: `false`).
  - `confluence_db_address` IP адрес или DNS имя сервера БД.
  - `confluence_db_port` Порт БД.
  - `confluence_db_name` Имя БД.
  - `confluence_db_username` Имя пользователя БД.
  - `confluence_db_password` Пароль пользователя БД.
- `confluence_tomcat_connector_proxyname` Fqdn имя сервера. Если обратный прокси не используется, то нужно эту переменную оставить без значения.
- `confluence_tomcat_connector_scheme` Протокол.

  Доступные значения:
  - `http` (default)
  - `https`

    **Внимание** При использовании `https` протокола нужно установить SSL сертификат на сервере с обратным прокси.

- `confluence_tomcat_connector_proxyport` Порт сервера (default: `80` или `443`).
  - `80` при установке переменной `confluence_tomcat_connector_scheme` в значение `http`.
  - `443` при установке переменной `confluence_tomcat_connector_scheme` в значение `https`.

Зависимости
-----------

Роль не устанавливает `java`, обратный прокси (`apache` или `nginx`) и систему управления БД, вы должны установить пакеты самостоятельно перед запуском роли.

Пример использования
--------------------

- Устанавливаем `Confluence`, `java` и настраиваем подключение к БД через веб-интерфейс:

  - Устанавливаем зависимости:

    ```bash
    ansible-galaxy install -r requirements.yml
    ```

  - Запускаем playbook:

    ```yaml
    ---

    - name: Setup Confluence
      hosts: confluence

      roles:
        - role: geerlingguy.java
        - role: ansible-role-confluence
    ```

Лицензия
--------

MIT

Информация об авторе
--------------------

Мелехин Антон.
