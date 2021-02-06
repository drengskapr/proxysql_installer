Role Name
=========

This role installs ProxySQL and provides basic configuration for it.

Requirements
------------

Ubuntu 20.04 or Debian 10

Might work on older versions, but I didn't test it.

Role Variables
--------------

`proxysql_admin_user` proxysql administrative user.

`proxysql_admin_password` password for proxysql administrative user.

`proxysql_stats_user` proxysql statistics webpage login.

`proxysql_stats_user_password` proxysql statistics webpage password.

`monitor_user` proxysql monitoring user. Must exist in your PXC cluster.

`monitor_user_password` monitoring user's password. Must match with monitoring user's password in your PXC cluster.

`node1_address` PXC node's address. Configuration of this role assumes that there are three nodes in your PXC cluster.

`node2_address` PXC node's address. Configuration of this role assumes that there are three nodes in your PXC cluster.

`node3_address` PXC node's address. Configuration of this role assumes that there are three nodes in your PXC cluster.

`proxysql_client_user` proxysql user to login to PXC cluster. Must exist in PXC cluster.

`proxysql_client_user_password` client user's password. Must match client user's password in PXC cluster.

Example Playbook
----------------

```
- name: Setting up Proxysql
  hosts: all
  remote_user: remote_user
  roles:
    - proxysql_installer
  vars:
    proxysql_admin_user: user1
    proxysql_admin_password: password1
    proxysql_stats_user: user2
    proxysql_stats_user_password: password2
    monitor_user: user3
    monitor_user_password: password3
    node1_address: 10.0.0.1
    node2_address: 10.0.0.2
    node3_address: 10.0.0.3
    proxysql_client_user: user4
    proxysql_client_user_password: password4
```

License
-------

BSD

