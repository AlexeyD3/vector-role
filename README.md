ansible-vector
=========
![GitHub tag (latest by date)](https://img.shields.io/badge/tag-1.0.0-blue)
[![Ansible Galaxy Vector](https://img.shields.io/badge/role-AlexeyD3.vector-blue.svg)](https://galaxy.ansible.com/AlexeyD3/vector/)
[![Ansible Galaxy Clickhouse](https://img.shields.io/badge/role-AlexeyD3.clickhouse-yellow.svg)](https://galaxy.ansible.com/AlexeyD3/clickhouse/)
[![Ansible Galaxy Lighthouse](https://img.shields.io/badge/role-AlexeyD3.lighthouse-yellow.svg)](https://galaxy.ansible.com/AlexeyD3/lighthouse/)

Роль для установки Vector.
- Установка Vector
- Создание systemd unit Vector
- Конфигурирование Vector на передачу данных в clickhouse

Requirements
------------
Требуется роль [clickhouse-role](https://github.com/AlexeyD3/clickhouse-role)

Role Variables
--------------
Переменные для установки
default/main.yml:
```yaml
clickhouse_user: netology
clickhouse_password: netology
```

Конфигурация для сбора и передачи логов содержится в vars/main.yml

Dependencies
------------
В `inventory` должен быть хост `clickhouse-01`
```yaml
endpoint: http://{{ hostvars['clickhouse-01'].ansible_host }}:8123
```

Example Playbook
----------------
```yaml
hosts: vector
roles:
  - role: vector-role
```

Author Information
------------------
Alexey Dubrovin
