[![Build Status](https://travis-ci.org/CSCfi/ansible-role-dell-firmware-upgrade.svg?branch=master)](https://travis-ci.org/CSCfi/ansible-role-dell-firmware-upgrade)
ansible-role-dell-firmware-upgrade
=========

Ansible role to upgrade Dell system firmwares. This uses the Dell DSU utility and it sets it up if it's not already present.


Role Variables
--------------

See defaults/main.yml for details.

By default this role does not install the Dell DSU yum repo. To install Dell DSU, the variable dell_dsu_repo_install should be set to True.

By default, this role upgrades all firmwares. To disable this functionality, the variable dell_dsu_update_all_firmware should be set to False.

If some firmwares are defined in upgrade_categories, then only these firmwares should be upgraded. If upgrade_categories is defined, then dell_dsu_update_all_firmware is ignored.

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

* You can simply use this role like below. In this case, the code will upgrade all firmwares.
```
- hosts: servers
  roles:
     - { role: ansible-role-dell-firmware-upgrade }
```

* If you plan to do not upgrade all firmwares, then you can use the following code: 
```
- hosts: servers
  vars:
    - dell_dsu_update_all_firmware: False
  roles:
     - { role: ansible-role-dell-firmware-upgrade }
```

* If you plan to upgrade only iDRAC and BIOS firmwares, then you can use the following code: 
```
- hosts: servers
  vars:
    - upgrade_categories: "BIOS,iDRAC"
  roles:
     - { role: ansible-role-dell-firmware-upgrade }
```

More information about possible firmware components is available [here](defaults/main.yml#L34-L52).

License
-------

MIT

Author Information
------------------

This role was created by Kalle Happonen
