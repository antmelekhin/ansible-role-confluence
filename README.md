Confluence
==========

Ansible роль для установки, настройки и обновления [Confluence](https://www.atlassian.com/ru/software/confluence).

Требования
----------

- Поддерживаемая версия Ansible: 2.7 и выше.
- Список поддерживаемых платформ описан в файле метаданных роли.

Используемые переменные
-----------------------

- `confluence__version` Версия Confluence для установки (default: `7.4.5`).
- `confluence__archive_url` Ссылка на скачивание архива с приложением.
- `confluence__username` Unix имя пользователя (default: `confluence`).
- `confluence__group` Unix группа пользователя (default: `confluence`).
- `confluence__root_path` Каталог, в который будет распакован архив и установлено приложение (default: `/opt/atlassian`).
- `confluence__home_path` Домашний каталог Confluence (default: `/var/atlassian/application-data/confluence`).
- `confluence__jvm_minimum_memory` Минимальный объем памяти, используемый JVM (default: `1024m`).
- `confluence__jvm_maximum_memory` Максимальный объем памяти, используемый JVM (default: `1024m`).
- `confluence__tomcat_connector_proxyname` Fqdn имя сервера. Если обратный прокси не используется, то нужно эту переменную оставить без значения.
- `confluence__tomcat_connector_scheme` Протокол.

  Доступные значения:
  - `http` (default)
  - `https`

    **Внимание** При использовании `https` протокола нужно установить SSL сертификат на сервере с обратным прокси.

- `confluence__tomcat_connector_proxyport` Порт сервера (default: `80` или `443`).
  - `80` при установке переменной `confluence__tomcat_connector_scheme` в значение `http`.
  - `443` при установке переменной `confluence__tomcat_connector_scheme` в значение `https`.

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

Мелехин Антон, ООО "ЖИЛИЩНАЯ ЭКОСИСТЕМА ВТБ".
