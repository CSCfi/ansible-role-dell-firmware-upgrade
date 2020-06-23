[![Build Status](https://travis-ci.org/CSCfi/ansible-role-dell-firmware-upgrade.svg?branch=master)](https://travis-ci.org/CSCfi/ansible-role-dell-firmware-upgrade)
ansible-role-dell-firmware-upgrade
=========

Ansible role to upgrade Dell system firmwares. This uses the Dell DSU utility and it sets it up if it's not already present.


Role Variables
--------------

See defaults/main.yml for details.

By default this role does not install the Dell DSU yum repo.

By default this role upgrades all firmwares.

Define something like this to use a proxy when fetching the Dell bootstrap script
<pre>
proxy_server_address: "http://your_special_proxy:3128"
proxy_env:
  ftp_proxy: "{{proxy_server_address}}"
  http_proxy: "{{proxy_server_address}}"
  https_proxy: "{{proxy_server_address}}"
</pre>

Dependencies
------------


Example Playbook
----------------

* You can simply use this role like
```
- hosts: servers
  roles:
     - { role: ansible-role-dell-firmware-upgrade }
```
License
-------

MIT

Author Information
------------------

This role was created by Kalle Happonen
