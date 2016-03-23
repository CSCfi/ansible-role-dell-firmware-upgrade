ansible-role-dell-firmware-upgrade
=========

Ansible role to upgrade Dell system firmwares. This uses the Dell DSU utility and it sets it up if it's not already present.


Role Variables
--------------
By default this role upgrades all firmwares.

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
