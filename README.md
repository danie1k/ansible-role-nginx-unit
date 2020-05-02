nginx-unit
==========

[![Build Status](https://img.shields.io/travis/danie1k/ansible-role-nginx-unit)][1]
[![MIT License](https://img.shields.io/github/license/danie1k/ansible-role-nginx-unit)][2]
[[![Ansible Galaxy](https://img.shields.io/badge/galaxy-nginx__unit-660198.svg)][3]

Installs [NGINX Unit](https://unit.nginx.org/) server.

Supported Languages
-------------------

* **Python**  
    Currently role supports only Python installed via [pyenv](https://github.com/pyenv/pyenv) (for example using [avanov.pyenv](https://galaxy.ansible.com/avanov/pyenv) role).

    To **automatically** compile modules for **all** installed Python versions, set `pyenv_path` variable value.

Role Variables
--------------

| Variable name | Description | Default value |
|---------------------|-------------|---|
| pyenv_path          | Absolute path to pyenv installation directory      | ``                            |
| nginx_unitd_daemon  | Run in daemon mode                                 | `false`                       |
| nginx_unitd_control | Address of control API socket                      | `unix:/run/unit/control.sock` |
| nginx_unitd_pid     | PID filename                                       | `/run/unit/unit.pid`          |
| nginx_unitd_log     | Log filename                                       | `/var/log/unit/unit.log`      |
| nginx_unitd_modules | Modules directory name                             | `/usr/lib64/unit/modules`     |
| nginx_unitd_state   | State directory name                               | `/var/lib/unit`               |
| nginx_unitd_user    | Non-privileged processes to run as specified user  | `nobody`                      |
| nginx_unitd_group   | Non-privileged processes to run as specified group | _user's primary group_        |


Example Playbook
----------------

```yaml
- hosts: servers
  roles:
     - name: danie1k.nginx_unit
       vars:
         pyenv_path: /usr/local/pyenv
```

License
-------

MIT

[1]: http://travis-ci.org/danie1k/ansible-role-nginx-unit
[2]: https://github.com/danie1k/ansible-role-nginx-unit/blob/master/LICENSE
[3]: https://galaxy.ansible.com/danie1k/nginx_unit
