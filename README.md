Role Name
=========

`codezm.nginx` 通过编译 `nginx` 源码进行安装部署.

Role Variables
--------------

see `defaults/main.yml`、`vars/main.yml`.

| Variables                 |  Description                                                                  |
| ------------------------- | ----------------------------------------------------------------------------- |
| __ansible_get_url_timeout | `wget` 命令超时时间                                                           |
| __package_tmp_save_dir    | 目标服务器临时目录                                                            |
| __clean_origin_file       | true: 代表清除原始文件，false: 代表保留                                       |
| env_install_way           | 安装方式。file: 文件模式（将从 `files` 目录拷贝），network: 从网络下载（默认）|
Dependencies
------------

- `codezm.common`

Example Playbook
----------------

```yml
vars:
  - __web_user: apache
  - __web_user_uid: 48
  - __web_group: apache
  - __web_group_gid: 48
  - __clean_origin_file: true
  - __package_tmp_save_dir: "/tmp/"
  - __ansible_get_url_timeout: 90
  - env_install_way: "file"

roles:
  - role: codezm.nginx
    tags: nginx
```
License
-------

MIT
